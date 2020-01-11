---
layout: post
title:  "Linked Lists"
date:   2018-06-05
tags:  [data structure]
---
# What is a linked list?
## Node

|data|
|nextNode|

Head, Node, nextNode, NULL
```java
public class Node {
  private int data;
  private Node nextNode;

  public Node (int data) {
    this.data = data;
  }

  public int getData() {
    return this.data;
  }

  public Node getNextNode() {
    return this.nextNode;
  }

  public void setData(int data) {
    this.data = data;
  }

  public void setNextNode(Node nextNode) {
    this.nextNode = nextNode;
  }

  @Override
  public String toString() {
    return "Data: " + this.data;
  }
}
```
# Implementing a linked list in Java
LinkedList.java
```java
public class LinkedList {
  private Node head;

  public void insertAtHead (int data) {
    Node newNode = new Node (data);
    newNode.setNextNode(this.head);
    this.head = newNode;
  }

  public int length() {
		  int length = 0;
		  Node current = this.head;

		  while(current != null) {
			  length++;
			  current = current.getNextNode();
		  }
		  return length;
	  }

    public void deleteFromHead() {
		  this.head = this.head.getNextNode();
	  }

    public Node find (int data) {
		  Node current = this.head;

		  while(current != null) {
			  if (current.getData() == data) {
				  return current;
			  }
			  current = current.getNextNode();
		  }
		  return null;
	  }

  @Override
  public String toString() {
    String result = "{";
    Node current = this.head;

    while (current != null) {
      result += current.toString() + ",";
      current = current.getNextNode();
    }

    result += "}";
    return result;
  }
}
```
# Inserting a new node
`addAtStart(Integet data)`: $$O(1)$$
LinkedListDemo.java
```java
public class LinkedListDemo {
  public static void main(String[] args) {
    LinkedList list = new LinkedList();

    list.insertAtHead(5);
    list.insertAtHead(10);
    list.insertAtHead(2);
    list.insertAtHead(12);
    list.insertAtHead(19);
    list.insertAtHead(20);

    System.out.println(list);
  }
}
```
# Length of a linked list
# Deleting the head node
`deleteAtStart()`: $$O(1)$$
# Searching for an item
Search(data): $$O(n)$$  
Search(12), Search(12)
# Doubly ended lists
```java
public class DoublyEndedList {
	private Node head;
	private Node tail;

	public void insertAtTail (int data) {
		Node newNode = new Node(data);
		if (this.head == null) {
			this.head = newNode;
		}

		if (this.tail != null) {
			this.tail.setNextNode(newNode);
		}
		this.tail = newNode;
	}

	@Override
	public String toString() {
		String result = "{";
	    Node current = this.head;

	    while (current != null) {
	      result += current.toString() + ",";
	      current = current.getNextNode();
	    }

	    result += "}";
	    return result;
	}
}
```
# Inserting data in a sorted linked list
## Empty Linked List
## Sorted Linked List
`insert(Integer data)`: $$O(n)$$
# Doubly linked list
## Doubly Linked Node
prevNode, nextNode  
Insert a New Element
<!-- Insertion sort revisited -->
