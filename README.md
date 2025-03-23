Q1.md

1 Drop Constants as big O focuses on the dominant term, ignoring constant factors example if an algorithm runs in O(5n + 10), we simplify it to O(n)


2 Drop Non-Dominant Terms as only the highest growth rate term matters example if an algorithim runs in O(n² + n), we simplify it to O(n² because as n grows, n² dominates

3 Different inputs should have differrent varriables like when multiple inputs exist, they should be represented separately for rxample for a function processing two lists of size m and n, complexity is O(m + n), not O(n)

4 Worst_Case Analysis is Preferred as big O typically describes the worst-case scenario of an algorithm for example in linear search, the best casse is O(1) (if the element is the first one), but the worst case is O(n)

5 Recursive functions follow the master theorem as for recursive algorithms, complexity is determined using recurrence relations ie merge sort follows T(n) = 2T(n/2) + O(n), which simplifies to O(n log n)



Q2.md

Memory Allocation; Arrays have contiguous memory allocation which is fixed in size while linked lists have dynamic memory allocation which can grow as it is needed

Performance; Arrays have fast accesss via indexing O(1), but resizing them is costly while linked lists have have slower access O(n), but efficient resizing

Insertion and deletion; Arrays are costly as shifting elements is required O(n) while linked lists are efficient at head or tail O(1), O(n) elsewhere 



Q3

class Node {
    int data;
    Node next;

    public Node(int data) {
        this.data = data;
        this.next = null;
    }
}

class SinglyLinkedList {
    private Node head;

    // Insert a node at the beginning
    public void insertAtBeginning(int data) {
        Node newNode = new Node(data);
        newNode.next = head;
        head = newNode;
    }

    // Insert a node at the end
    public void insertAtEnd(int data) {
        Node newNode = new Node(data);
        if (head == null) {
            head = newNode;
            return;
        }
        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;
        }
        temp.next = newNode;
    }

    // Delete a node from the beginning
    public void deleteFromBeginning() {
        if (head == null) {
            System.out.println("List is empty. Nothing to delete.");
            return;
        }
        head = head.next;
    }

    // Display the linked list
    public void display() {
        Node temp = head;
        while (temp != null) {
            System.out.print(temp.data + " -> ");
            temp = temp.next;
        }
        System.out.println("null");
    }

    public static void main(String[] args) {
        SinglyLinkedList list = new SinglyLinkedList();
        list.insertAtBeginning(10);
        list.insertAtBeginning(20);
        list.insertAtEnd(30);
        list.display();

        list.deleteFromBeginning();
        list.display();
    }
}
