# cs2113f16
Files for GW CS2113 Software Engineering

1. addNode: This should add a location to the end of the list.

Inputs: name, latitude, and longitude of the new location
Return the index of where the element was added 
(i.e., if the list was empty, it should return 0; if the new entry is the 4th entry, it should return 3), 
or -1 on an error.


function takes arguments for string name, int latitude, int longitude, and Llist;
initialize a counter to -1;
initialize a node pointer;
create a new node and populate its variables with the arguments;
if the list head isn't null, set the pointer to the list head;
if the list head is null, set the LList head pointer to the new node and set counter to 0;
while the node being pointed to doesn't have a null next, counter++ and set the pointer to the next node in the list, starting with the list head;
set the next of the node with a null next to point to the new node;
return counter;

2. addSortedNode: Add a location to the list sorted by longitude (i.e. the one that changes as you go east/west).

Inputs: name, latitude, and longitude of the new location
Return the index of where the element was added (i.e., if the list was empty, it should return 0; if the new entry is the 4th entry, it should return 3), or -1 on an error.

helper function to check that the list is sorted already that returns boolean and take an argument of the Llist;
initialize a boolean to true
if the head is null, return true;
if the head's next is set to null, return true;
initialize an int variable currentLong;
set a node pointer to the head;
while the pointer isn't pointing to a node with a null next, compare the longitude of the pointer's node with that node's next. If the next one is smaller, set the boolean to false;
return the boolean;

addSortedNode takes arguments of string name, latitude, and longitude;
initialize a counter to -1;
initialize a node pointer;
create a new node and populate its variables with the arguments;
if the list isn't sorted, return counter;
if the list head isn't null, set the pointer to the list head;
if the list head is null, set the LList head pointer to the new node, set counter to 0, and return the counter;
while the next of the node being pointed to's longitude isn't greater than the longitude argument or it's null, counter++ and set the pointer to the next node in the list, starting with the list head;
set the next of the new node to the next of the node being pointed to;
set the next of the node being pointed to to the new node;
counter++;
return counter;

3. remNode: Remove a location by name

Input: The name of the location to remove.
Note: If there happen to be two entries in the list with the same name, you should remove the entry closest to the head of the list.
Implementation tip: you cannot test if two strings are equal with == in C or Java!
Return the index where the element was removed, or -1 on an error.

function takes arguments for the Llist and the string name;
initialize int index to -1;
initialize a node pointer;
if the head is null, return index;
else if the head is a match, set the head to point to the next of the head, and set the index to 0;
else, set the index to 1, create a boolean set to false, set the pointer to the head, and while boolean is false;
  if the next of the node being pointed to is null, set the index to -1 and change boolean to true;
  else If the name of the next of the node being pointed to is not a match, set the pointer to the next of the node being pointed to and index++;
  else if the name of the next of the node being pointed to is a match, set the next of the node being pointed to to the next of the next of the node being pointed to, and set the boolean to true;
return index;

4. clearList: Clear a list

Remove all locations in the list
Return the total number of entries that were removed.

function takes an argument for the Llist;
set an int counter to -1;
create a node pointer;
if the head isn't null, set the pointer to point to the head and set counter to 0;
while the head isn't null:
  use the remNode function on the name of the head;
  counter++;
return counter;
