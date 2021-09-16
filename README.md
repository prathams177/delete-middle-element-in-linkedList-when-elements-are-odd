# delete-middle-element-in-linkedList-when-elements-are-odd
delete middle element in linkedList  when elements are odd


#include <stdio.h>
#include<stdlib.h>

struct node{
    int data;
    struct node* next;
    
};

int middle(struct node *fp , struct node *sp , struct node *head){
    int midval=0;
    struct node *prev;
    while(fp->next!=NULL){
        
        prev=sp;
        sp=sp->next;
        fp=fp->next->next;
        
    }
    //printf("\nmiddle=%d",sp->data);
    midval=sp->data;
    prev->next=sp->next;
    printf("\nnew list after delete=\n");
    display(head);
    return midval;
}

void delete(){
    
}



void display(struct node *ptr){
    while(ptr!=NULL){
        printf("%d",ptr->data);
        ptr=ptr->next;
        
    }
    
}


int main()
{
    int midval=0;
    struct node *head , *first , *second , *third , *fourth;
    head = (struct node*) malloc(sizeof(struct node));
    first = (struct node*) malloc(sizeof(struct node));
    second = (struct node*) malloc(sizeof(struct node));
    third = (struct node*) malloc(sizeof(struct node));
    fourth = (struct node*) malloc(sizeof(struct node));
    
    head->data=1;
    head->next=first;
    
    first->data=2;
    first->next=second;
    
    second->data=3;
    second->next=third;
    
    third->data=4;
    third->next=fourth;
    
    fourth->data=5;
    fourth->next=NULL;
    
    display(head);
    midval=middle(head,head,head);
    printf("\nmiddle value=%d",midval);

    return 0;
}

