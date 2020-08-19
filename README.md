# Linear-Search-
Linear search using linked list
//linear search linked list
#include <iostream>
#include<bits/stdc++.h>
using namespace std;
class Node{
    public:
    int data;
    Node *next;
};
Node *head=NULL;
void insert(){
    int x;
    cout<<"Enter the element to insert"<<"\n";
    cin>>x;
    Node *p=new Node();
    p->data=x;
    p->next=NULL;
    if(head!=NULL){
        Node *t;
        t=head->next;
        head->next=p;
        p->next=t;
    }
    else{
        head=p;
    }
}
void traversal(){
    Node *t;
    t=head;
    while(t!=NULL){
        cout<<t->data<<"->";
        t=t->next;
    }
    cout<<"\n";
}
void search(){
    int x,c=0;
    cout<<"Enter the element to search"<<"\n";
    cin>>x;
    Node *t;
    t=head;
    while(t!=NULL){
        if(t->data==x){
            c=1;
            break;
        }
        t=t->next;
    }
    if(c==1){
        cout<<"Element Found"<<"\n";
    }
    else{
        cout<<"Element not found"<<"\n";
    }
}
int main() {
    int c,l;
l:    cout<<"Enter your choice"<<"\n";
    cout<<"1.Insertion"<<"\n";
    cout<<"2.Traversal"<<"\n";
    cout<<"3.Linear Search"<<"\n";
    cout<<"4.Exit"<<"\n";
    cin>>c;
    if(c==1){
        insert();
        goto l;
    }
   else if(c==2){
       traversal();
       goto l;
   }
   else if(c==3){
       search();
       goto l;
   }
   else{
       exit(0);
   }
}
