# Unhandled Exceptions and Missing Key Access in Asynchronous Dart Code

This repository demonstrates a common error in asynchronous Dart code and provides a solution. The original code lacks proper error handling, potentially leading to unexpected crashes when fetching data from an API.

## Bug

The `bug.dart` file contains Dart code that fetches data from an API.  The code demonstrates two potential issues: 

1. **Incomplete Exception Handling:** The `try-catch` block only catches general exceptions, potentially missing more specific ones.
2. **Unsafe JSON Access:** Accessing JSON data directly using bracket notation (`jsonData['key']`) without checking for the key's existence can lead to runtime errors if the key is not found in the JSON response.

## Solution

The `bugSolution.dart` file provides an improved version of the code that addresses these issues.  It includes:

1. **More robust exception handling:** Catches specific HTTP exceptions and handles them gracefully.
2. **Safe JSON access:** Uses `jsonData.containsKey('key')` to check for the key's existence before accessing its value. 

This example highlights the importance of thorough error handling and safe data access when working with asynchronous operations and external data sources in Dart.