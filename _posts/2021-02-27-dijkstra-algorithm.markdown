---
layout: post
title:  "Dijkstra's Algorithm on Digraph (C++)"
date:   2021-02-27 11:11:03 -0400
categories: graph algorithms
---
## Introduction
This project involves implementing an adjacency list representation of a weighted graph, and using it to apply Dijkstra's shortest paths algorithm (single-source, all destinations -- SSAD) to a weighted directed graph. The program reads the specification of the problem from a given file named for instance "*File.txt*". The input file will begin with two lines specifying the number of vertices in the graph, $$G=(V, E)$$, and the source vertex. Each of those values will be preceded by a label that ends with a colon character (':'). The next line will be blank. The remainder of the file will be a matrix (similar to the adjacency-matrix representation) of $$|V|$$ rows, each containing $$|V|$$ integer values for the weights of the edges in the graph. Weights will be integers in the range $$1$$ to $$99$$. Missing edges will be designated by the value $$0$$. Here's an example:

```sh
Number of vertices: 11
Start vertex:       4    

0    0    0   10    0   94    0    0   73    0    0
0    0    0   13    0    0    0    0    2    0    0
0    0    0    0    0   43    0    0    0    0    0
0    0    0    0    0    0    0    0    0    0    0
0    0    0   87    0    0    0    0    0   68    0
0    0    0    0    0    0    0    0    0    0    0
0   97    0    0    0    0    0    0    0    0    0
0    0    0    0    0   91    0    0    0    0    0
0    0    0    0    0    0    0    0    0    0    0
0   17    0    0    0    0    0    0    0    0    0
0    0    0    0    0    0   55    0    0    0    0
```

Output will be written to a file named for instance "*Result.txt*". The output file should consist of two sections, one displaying information about the given graph and the other displaying the results of running the Dijkstra's shortest paths SSAD algorithm.

The graph information display consists of a row of labels (see example), followed by $$\mid V\mid$$ rows of output displaying the graph information in a format similar to the adjacency-list representation of the graph. For each vertex, there will be one row of data listing the vertex number, followed by list of neighbor records. A neighbor record consists of a neighbor (vertex) number, followed by a colon character, followed by the weight of the corresponding edge. The graph information display is followed by a blank line.

The SSAD results display begins with two lines of labels (see example), one showing the source vertex and a blank line, followed by $$\mid V\mid$$ rows showing the results for each possible destination vertex (including the source vertex itself). Each of these lines consists of three sections, the destination vertex number, the length (total weight) of the shortest path found, and the actual path (a sequence of vertex numbers separated by spaces). If a vertex is not reachable from the source vertex, "`inf`" should be displayed instead of the length.

Here's an output example that corresponds to the input example above:

```sh
Node  | Out-neighbors
----------------------------------------------------------------------
0       3: 10  5: 94  8: 73
1       3: 13  8: 2
2       5: 43
3      
4       3: 87  9: 68   
5           
6       1: 97   
7       5: 91   
8          
9       1: 17
10      6: 55

Start vertex is: 4
Dest | Total Weight | Path
----------------------------------------------------------------------
0            inf        
1             85       9   1
2            inf          
3             87         
4             0        3   
5            inf   
6            inf         
7            inf          
8             87       9   1   8
9             68       9   
10           inf  
```

### Notes
- Implement a **digraph** template class for the weighted adjacency list representation of a directed graph.
- The data read from a file that specifying the graph is stored in a dynamic vertex `vector` as a private member of the class together with the source vertex.
- The **digraph** class includes function that writes the display of the graph in the proper format indicated above.
- Dijkstra's SSAD algorithm is implemented as a separate function. The function takes an initialized **digraph** object as one of its parameters and the source vertex as the second, and computes the path lengths and shortest paths. It doesn't write any of the display to the output file.

## Code Explanation
In this [program](https://github.com/zyz9066/Algorithms/blob/master/Graph%20Algorithm/main.cpp), the first major data structure is a `map` named *vertexMap* that allows us to find, for any vertex, a pointer to the *Vertex* object represents it.

```cpp
template<typename T>
struct MapDef {
    typedef map<int, Vertex<T>*, less<int>> vmap;
};
```

The second major data structure is the *Vertex* object that stores information about all the vertices.

### Vertex
A *Vertex* object maintains four pieces of information for each vertex.
- *number*: The corresponding to this vertex is established when the vertex is placed in `map` and never changes.
- *adj*: The `vector` of adjacent vertices is established when the graph is read.
- *dist*: The length of the shortest path from the starting vertex to this vertex is computed by Dijkstra's algorithm.
- *prev*: The previous vertex on the shortest path to this vertex.
- *known*: This variable is used to record whether this vertex has been visited or not during implementing Dijkstra's algorithm.
- *reset*: This function is used to initialize the data members that are computed by the Dijkstra's algorithm.

```cpp
template<typename T>
struct Vertex {
    int number;            // Vertex number
    vector<Edge<T>> adj;   // Adjacent list
    T dist;                // Distance
    Vertex* prev;          // Previous vertex on shortest path
    bool known;            // Flag used in Dijkstra's algorithm

    Vertex(const int& num) : number(num) { reset(); }

    void reset() { dist = 0x7fffffff; prev = NULL; known = false; }
};
```

### Edge
The *Edge* consists of a pointer to a *Vertex* and the edge cost.

```cpp
template<typename T>
struct Edge {
    Vertex<T>* dest;   // incident vertex in edge
    T cost;            // Edge cost

    Edge(Vertex<T>* d = 0, T c = 0) : dest(d), cost(c) {}
};
```

### digraph
In the *digraph* class interface, *vertexMap* stores the `map`. The rest of the class provides member functions that perform initialization, add vertices and edges, save the shortest path.

```cpp
template<typename T>
class digraph {
    public:
        digraph() {}
        ~digraph();

        MapDef<int>::vmap vertexMap;

        Vertex<T>* getVertex(const int& vertexNumber);
        void addEdge(const int& sourceNumber, const int& destNumber, int cost);
        string getPath(const int& destNumber) const;
        void clearAll();

    private:
        string getPath(const Vertex<T>& dest) const;

        digraph(const digraph& rhs) {}
        const digraph& operator= (const digraph& rhs) { return *this; }
};
```

- Constructor: The default creates an empty `map`.
- Destructor: It destroys all the dynamically allocated *Vertex* object.

```cpp
template<typename T>
digraph<T>::~digraph( ) {
    for (MapDef<int>::vmap::iterator itr = vertexMap.begin(); itr != vertexMap.end(); ++itr)
        delete (*itr).second;
}
```

- *getVertex*: This method consults the map to get the *Vertex* entry. If the *Vertex* does not exist, we create a new *Vertex* and update the `map`.

```cpp
template<typename T>
Vertex<T>* digraph<T>::getVertex(const int& vertexNumber) {
    MapDef<int>::vmap::iterator itr = vertexMap.find(vertexNumber);

    if (itr == vertexMap.end()) {
        Vertex<T>* newv = new Vertex<T>(vertexNumber);
        vertexMap[vertexNumber] = newv;
        return newv;
    }
    return (*itr).second;
}
```

- *addEdge*: This function gets the corresponding *Vertex* entries and then update the adjacency `vector`.

```cpp
template<typename T>
void digraph<T>::addEdge(const int& sourceNumber, const int& destNumber, int cost) {
    Vertex<T>* v = getVertex(sourceNumber);
    Vertex<T>* w = getVertex(destNumber);
    v->adj.push_back(Edge<T>(w, cost));
}
```
- *clearAll*: Initialize the members for the shortest path computation using Dijkstra's algorithm.

```cpp
template<typename T>
void digraph<T>::clearAll() {
    for (MapDef<int>::vmap::iterator itr = vertexMap.begin(); itr != vertexMap.end(); ++itr)
        (*itr).second->reset();
}
```
- *getPath*: This routine returns the shortest path after the computation has been performed. The *prev* member to trace back the path can be seen, it can give the path in order using recursion. The routine performs checking if a path actually exists and then returns *inf* if the path does not exist. Otherwise, it calls the recursive routine and returns the cost of the path.

```cpp
template<typename T>
string digraph<T>::getPath(const Vertex<T>& dest) const {   
    string str;
    if (dest.prev != NULL)
        str = getPath(*dest.prev) + "  ";

    stringstream ss;
    ss << dest.number;
    return str += ss.str();
}

template<typename T>
string digraph<T>::getPath(const int& destNumber) const {
    MapDef<int>::vmap::const_iterator itr = vertexMap.find(destNumber);
    if (itr == vertexMap.end())
        throw digraphException("Destination vertex not found!");

    string str;
    const Vertex<T>& w = *(*itr).second;
    if (w.dist == 0x7fffffff) {
        stringstream ss;
        ss << destNumber;
        str = ss.str() + "\t\tinf";
    } else {   
        stringstream ss, ssw;
        ss << destNumber;
        ssw << w.dist;
        str = ss.str() + "\t\t" + ssw.str() + "\t\t" + getPath(w);
    }
    return str += "\n";
}
```

### Path
This object is placed on the priority queue. It consists of the target vertex and its distance and a comparison function defined on the basis of the distance from start vertex.

```cpp
template<typename T>
struct Path {
    Vertex<T>* dest;   // target vertex
    T cost;            // distance

    Path(Vertex<T> *d = 0, T c = 0) : dest(d), cost(c) {}

    bool operator> (const Path& rhs) const { return cost > rhs.cost; }
    bool operator< (const Path& rhs) const { return cost < rhs.cost; }
};
```

### Dijkstra's SSAD algorithm
The *SSAD* function performs shortest path calculation using Dijkstra's algorithm. A method that works with the STL priority queue is used. This method involves inserting an *Path* object in the priority queue whenever we lower the distance. To select a new vertex *v* for visitation, we repeatedly remove the minimum item based on distance from the priority queue until an unvisited vertex emerges.

```cpp
template<typename T>
void SSAD(digraph<T>& g, const int& startNumber) {
    priority_queue<Path<T>, vector<Path<T>>, greater<Path<T>>> pq;
    Path<T> vrec;  // Stores the result of a deleteMin

    MapDef<int>::vmap::iterator itr = g.vertexMap.find(startNumber);
    if (itr == g.vertexMap.end()) {
        stringstream ss;
        ss << startNumber;
        throw digraphException(ss.str() + " is not a valid vertex!");
    }

    g.clearAll();
    Vertex<T>* start = (*itr).second;
    start->dist = 0;
    pq.push(Path<T>(start, 0));

    int nodesSeen = 0;
    for(; nodesSeen < g.vertexMap.size(); ++nodesSeen)
    {
        do { // Find an unvisited vertex
            if(pq.empty()) return;
            vrec = pq.top(); pq.pop();
        } while(vrec.dest->known);

        Vertex<T>* v = vrec.dest;
        v->known = true;

        for(int i = 0; i < v->adj.size(); ++i) {
            Edge<T> e = v->adj[i];
            Vertex<T>* w = e.dest;
            int cvw = e.cost;

            if (cvw < 0)
                throw digraphException("Negative edge seen!");

            // Update w
            if (w->dist > v->dist + cvw) {
                w->dist = v->dist + cvw;
                w->prev = v;
                pq.push(Path<T>(w, w->dist));
            }
        }
    }
}
```

### main
In *main* function, a simple program that reads a graph in adjacency matrix form from an input file named "*File.txt*", reads in the number of vertices and a start vertex, then runs Dijkstra's SSAD algorithm. To construct the *digraph* object, we repeatedly read one line of input, assign the line to an `istringstream` object, parse the line, and call *addEdge*. Using an *istringstream* allows us to verify that every line has at least the $$\mid V\mid$$ pieces corresponding to an vertex.

Once the graph has been read, we call *SSAD* to apply Dijkstra's algorithm for a starting vertex. This algorithm throws a *digraphException* if there is any error during execution. It catches any *digraphException* that might be generated and prints an appropriate error message.

## How to run
Name the input file as "*File.txt*", then run this program, it will generate text file "*Result.txt*" which contains desired output.
