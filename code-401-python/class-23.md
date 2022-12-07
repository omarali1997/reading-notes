# Read-24 Hashtabels

# Hashtables

## What is Hashing?
### A hash is a value that has a fixed length, and it is generated using a mathematical formula. Hash values are used in data compression, cryptology, etc. In data indexing, hash values are used because they have fixed length size regardless of the values that were used to generate them. It makes hash values to occupy minimal space compared to other values of varying lengths.

### A hash function employs a mathematical algorithm to convert the key into a hash. A collision occurs when a hash function produces the same hash value for more than one key.

#### A Hash Table in Python is nothing but a data structure where data is stored in an associative manner. In hash tables, data is stored in an array format, with every data value having an exclusive or unique index value. This type of storage offers quick access to data if the index of the data required is available.

#### Thus, the data structure provides easy and quick search and insertion irrespective of the data size. A Hash Table in Python utilizes an array as a medium of storage and uses the hash method to create an index where an element is to be searched from or needs to be inserted.

#### In other words, a Hash Table in Python is a data structure which stores data by using a pair of values and keys. Each data value is allocated an exclusive key that is created by using the hash functions. Then, to access its associated value the name of the key is used, thus making searching of data values a very fast and efficient process.


## Why do we use them?
1. Hold unique values
2. Dictionary
3. Library

## What Are they
### Hashtables are a data structure that utilize key value pairs. This means every `Node` or `Bucket` has both a key, and a value.

### The basic idea of a hashtable is the ability to store the key into this data structure, and quickly retrieve the value. This is done through what we call a `hash`. A `hash` is the ability to encode the key that will eventually map to a specific location in the data structure that we can look at directly to retrieve the value.

### Since we are able to `hash` our key and determine the exact location where our value is stored, we can do a lookup in an O(1) time complexity. This is ideal when quick lookups are required.

## Example
### Let’s say we have data of Seattle neighborhood names and their corresponding zip codes.
```
["Greenwood:98103", "Downtown:98101", "Alki Beach:98116", "Bainbridge Island:98110", ...]
```

### Now, we want to be able to search through the data to look up a neighborhood and obtain it’s zip code. We could do this using a for loop that looks through each piece of data one by one until it finds the neighborhood name, then returns the zip code there. This would be an `O(N)` read operation because it requires searching through each piece of data to find the one piece we want.

### Arrays actually have fast access. If we know the index of the information we want we can access that information in `O(1)` time. The reason why searching for a piece of data in a collection is `O(N)` isn’t because the array is slow, it’s just that we have to look through all N things in the collection.

### Hash maps take advantage of an array’s `O(1)` read access. Instead of adding elements to an array from beginning to end, a hash map uses a “hash function” to place each item at a precise index location, based off it’s key.

### Basically, the hash function takes a key and returns an integer. We use the integer to determine where the key/value pair should be placed in the array. The hash code is calculated in constant time and writing to an array at one index is `O(1)` so the hash map has `O(1)` access.

### The hash code is used again to read something from the hash map. Take the key, run it through the hash code to get a number, use that number to index the array. Calculating the hash code and reading an array at that index is all constant time to the hash map has `O(1)` read access!


## Structure
## Hashing
### Basically, a hash code turns a key into an integer. It’s very important that hash codes are deterministic: their output is determined only by their input. Hash codes should never have randomness to them. The same key should always produce the same hash code.

## Creating a Hash
### A hashtable traditionally is created from an array. I always like the size 1024. this is important for index placement. After you have created your array of the appropriate size, do some sort of logic to turn that “key” into a numeric number value. Here is a simplistic hashing algorithm:

1. Add or multiply all the ASCII values together.
2. Multiply it by a prime number such as 599.
3. Use modulo to get the remainder of the result, when divided by the total size of the array.
4. Insert into the array at that index.
### Example:
```
Key = "Cat"
Value = "Josie"

67 + 97 + 116 = 280

280 * 599 = 69648

69648 % 1024 = 16

Key gets placed in index of 16. 
```

### We now know that our key `Cat` maps to index 16 of the array. We can view into this index and find “Josie”, our value quickly.

### NOTE: Production systems will have much more robust hashing algorithms that ensure even distribution of values across all buckets and avoid unnecessary collisions.

### Let’s dive a bit deeper into HOW the key/values are stored in the array.

### Each index of the array can hold many types of values. The trick is how the values are stored in comparison to efficiency. Each Index of the array contain “buckets”. Each of these “buckets” holds one key/value pair combination. When there is no entry in a specific bucket, the buckets (each index of the array) all start `null`. The hash table starts each bucket empty and overwrites their value once a key generates a hashCode that corresponds with an index.