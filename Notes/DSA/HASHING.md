# Hashing:
- In data structure, hashing helps in narrowing down search and find number within seconds. 
- Hashing is the process of converting input data of any size into a fixed-size value, usually for the purpose of fast data retrieval.
- It involves using a **hash function** to map data items to a fixed-size array which is called a **hash table**.


## How It works?
- Hash Function: You provide your data items into the hash function.
- Hash Code: The hash function crunches the data and give a unique hash code.
- Hash Table: The hash code then points you to a specific location within the hash table.

### Hash Table in Data Structure
-  A hash table is also known as a hash map. It is a data structure that stores key-value pairs. It uses a hash function to map keys to a fixed-size array, called a hash table. This allows in faster search, insertion, and deletion operations.

### Hash Function
- The hash function is a function that takes a key and returns an index into the hash table. The goal of a hash function is to distribute keys evenly across the hash table, minimizing collisions (when two keys map to the same index).

#### Common hash functions include:
- Division Method: Key % Hash Table Size
- Multiplication Method: (Key * Constant) % Hash Table Size
- Universal Hashing: A family of hash functions designed to minimize collisions

## What is a Hash Collision?
-  A hash collision occurs when two different keys map to the same index in a hash table. This can happen even with a good hash function, especially if the hash table is full or the keys are similar.

### Causes of Hash Collisions:
- Poor Hash Function: A hash function that does not distribute keys evenly across the hash table can lead to more collisions.
- High Load Factor: A high load factor (ratio of keys to hash table size) increases the probability of collisions.
- Similar Keys: Keys that are similar in value or structure are more likely to collide.

#### Collision Resolution Techniques
There are two types of collision resolution techniques:
- Open Addressing:
	- Linear Probing: Search for an empty slot sequentially
	- Quadratic Probing: Search for an empty slot using a quadratic function
- Closed Addressing:
	- Chaining: Store colliding keys in a linked list or binary search tree at each index
	- Cuckoo Hashing: Use multiple hash functions to distribute keys

## Applications of Hashing
Hash tables are used in a wide variety of applications, including:
- Databases: Storing and retrieving data based on unique keys
- Caching: Storing frequently accessed data for faster retrieval
- Symbol Tables: Mapping identifiers to their values in programming languages
- Network Routing: Determining the best path for data packets



Problems:
1. find duplicate or count/frequency array elements.
2. highest or lowest frequency array elements.