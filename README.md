# advance-algorithms-w2-linked-list


#include <iostream>
using namespace std;

struct Node {
    int row, col, value;
    Node* next;
};

// Insert node at end of list
void insert(Node*& head, int row, int col, int value) {
    if (value == 0) return; // skip zero values
    Node* newNode = new Node{row, col, value, nullptr};
    if (!head) {
        head = newNode;
        return;
    }
    Node* temp = head;
    while (temp->next) temp = temp->next;
    temp->next = newNode;
}

// Display sparse matrix in list form
void display(Node* head) {
    cout << "Row\tCol\tValue\n";
    while (head) {
        cout << head->row << "\t" << head->col << "\t" << head->value << "\n";
        head = head->next;
    }
}

int main() {
    Node* head = nullptr;

    // Example sparse matrix input
    insert(head, 0, 2, 3);
    insert(head, 0, 3, 4);
    insert(head, 2, 1, 5);
    insert(head, 3, 2, 6);

    cout << "Sparse Matrix stored as Linked List:\n";
    display(head);

    return 0;
}
