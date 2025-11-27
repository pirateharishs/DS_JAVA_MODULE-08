## NAME: HARISH S
## REG-NO: 212223230071



## 1.Write a program to perform postorder traversal (Left → Right → Root) of a binary tree built from level order input.
### Input Format:
###   First line: N
###   Second line: N space-separated integers
### Output Format:
###   Postorder traversal as space-separated values

### program:

```
import java.util.*;

class Node {
    int data;
    Node left, right;
    Node(int data) {
        this.data = data;
    }
}

public class Main {

    static Node buildTree(int[] arr) {
        if (arr.length == 0) return null;

        Node root = new Node(arr[0]);
        Queue<Node> q = new LinkedList<>();
        q.add(root);

        int i = 1;
        while (!q.isEmpty() && i < arr.length) {
            Node curr = q.poll();

            curr.left = new Node(arr[i++]);
            q.add(curr.left);
            if (i >= arr.length) break;

            curr.right = new Node(arr[i++]);
            q.add(curr.right);
        }
        return root;
    }

    static void postorder(Node root) {
        if (root == null) return;
        postorder(root.left);
        postorder(root.right);
        System.out.print(root.data + " ");
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];

        for (int i = 0; i < n; i++)
            arr[i] = sc.nextInt();

        Node root = buildTree(arr);
        postorder(root);
    }
}

```
### output:
<img width="907" height="190" alt="image" src="https://github.com/user-attachments/assets/023ec5e2-901f-4137-867a-e78ee36023f9" />


## 2.You are given a list of node values to be inserted into a binary tree in level order (left to right). Build the binary tree and print the inorder traversal of the tree.
### Input Format:
###   First line: Integer N (number of nodes)
###   Second line: N space-separated integers
### Output Format:
###   A single line with the inorder traversal (space-separated)

### program:

```
import java.util.*;

class Node {
    int data;
    Node left, right;

    Node(int data) {
        this.data = data;
    }
}

public class Main {

    static Node buildTree(int[] arr) {
        if (arr.length == 0) return null;

        Node root = new Node(arr[0]);
        Queue<Node> q = new LinkedList<>();
        q.add(root);

        int i = 1;
        while (!q.isEmpty() && i < arr.length) {
            Node curr = q.poll();

            curr.left = new Node(arr[i++]);
            q.add(curr.left);
            if (i >= arr.length) break;

            curr.right = new Node(arr[i++]);
            q.add(curr.right);
        }
        return root;
    }

    static void inorder(Node root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.data + " ");
        inorder(root.right);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) arr[i] = sc.nextInt();

        Node root = buildTree(arr);
        inorder(root);
    }
}

```

### output:
<img width="845" height="151" alt="image" src="https://github.com/user-attachments/assets/1b3a22a8-dd37-460f-b94e-08c0b68742b2" />

## A university stores student roll numbers in a system that allows efficient insertion and retrieval. Your task is to insert all student roll numbers into a Binary Search Tree and         print the inorder traversal, which will give the roll numbers in sorted order.
### Input Format:
###  First line: N (number of students)
###  Second line: N integers representing student roll numbers
### Output Format:
###  Inorder traversal of BST (space-separated integers)

### program:
```
import java.util.*;

class Node {
    int data;
    Node left, right;

    Node(int val) {
        data = val;
        left = right = null;
    }
}

public class Main {

    static Node insert(Node root, int val) {
        if (root == null) return new Node(val);

        if (val < root.data)
            root.left = insert(root.left, val);
        else
            root.right = insert(root.right, val);

        return root;
    }

    static void inorder(Node root) {
        if (root == null) return;
        inorder(root.left);
        System.out.print(root.data + " ");
        inorder(root.right);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int N = sc.nextInt();
        Node root = null;

        for (int i = 0; i < N; i++) {
            int x = sc.nextInt();
            root = insert(root, x);
        }

        inorder(root);
    }
}

```

### output:
<img width="645" height="137" alt="image" src="https://github.com/user-attachments/assets/ade06424-3d25-435d-948a-388696d91aa2" />

