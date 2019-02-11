# SOLUTIONS 
## Write a program that inputs a line of text and uses a stack to print the line reversed.

```C
 
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>

#define YES 1
#define NO 0

// stackNode structure definition
struct stackNode { 
   char data; // node data
   struct stackNode *nextPtr; // pointer to next node
}; // end struct stackNode

typedef struct stackNode STACKNODE;
typedef STACKNODE *STACKNODEPTR;

// function prototypes
void push( STACKNODEPTR *topPtr, char info );
char pop( STACKNODEPTR *topPtr );
int isEmpty( STACKNODEPTR topPtr );

int main( void )
{ 
   STACKNODEPTR stackPtr = NULL; // points to the stack top
   char c; // current character from text
   char line[ 50 ]; // text from user
   char condensedLine[ 50 ]; // text with only letters
   int i = 0; // length of condensed line
   int j = 0; // length of line
   int palindrome = YES; // result of palindrome test

   puts( "Enter a line of text:" );

   // read each letter with getchar and add to line
   while ( ( c = getchar() ) != '\n' ) { 
      line[ j++ ] = c;

      // remove all spaces and punctuation
      if ( isalpha( c ) ) { 
         condensedLine[ i++ ] = tolower( c );
         push( &stackPtr, tolower( c ) );
      } // end if

   } // end while

   line[ j ] = '\0';

   // loop through condensedLine
   for ( j = 0; j < i; ++j ) {

      // if condensedLine does not equal stack
      if ( condensedLine[ j ] != pop( &stackPtr ) ) { 
         palindrome = NO;
         break; // exit loop
      } // end if

   } // end for

   // if text is a palindrome
   if ( palindrome ) {
      printf( "\"%s\" is a palindrome\n", line );
   } // end if
   else {
      printf( "\"%s\" is not a palindrome\n", line );
   } // end else
} // end main

// Insert a node at the stack top
void push( STACKNODEPTR *topPtr, char info )
{ 
   STACKNODEPTR newPtr; // temporary node pointer

   // dynamically allocate memory
   newPtr = malloc( sizeof( STACKNODE ) );

   // if memory was allocated, insert node at top of stack
   if ( newPtr ) { 
      newPtr->data = info;
      newPtr->nextPtr = *topPtr;
      *topPtr = newPtr;
   } // end if
   else {
      printf( "%d not inserted. No memory available.\n", info );
   } // end else
} // end function push

// Remove a node from the stack top
char pop( STACKNODEPTR *topPtr )
{ 
   STACKNODEPTR tempPtr; // temporary node pointer
   int popValue; // value of popped node

   tempPtr = *topPtr;
   popValue = ( *topPtr )->data;
   *topPtr = ( *topPtr )->nextPtr; // reset topPtr
   free( tempPtr ); // free memory

   return popValue; // return value of popped node
} // end function pop

// Is the stack empty?
int isEmpty( STACKNODEPTR topPtr )
{ 
   return !topPtr; // return NULL if stack is empty
} // end function isEmpty

```
