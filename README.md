# Advanced-Software-Engineering-Walmart
technical discovery, design and implementation of large-scale applications, products and platforms

The code you provided consists of two separate classes: `PowerOfTwoMaxHeap` and `DatabaseConnector`. Let's summarize and explain each class:

1. `PowerOfTwoMaxHeap`:
   - This class represents a max heap data structure with a power-of-two branching factor. It has the following methods:
     - `constructor(x)`: Initializes the heap with an empty array (`heap`) and a parameter `x`.
     - `insert(value)`: Inserts a value into the heap and maintains the heap property by performing a sift-up operation.
     - `popMax()`: Removes and returns the maximum value from the heap, then maintains the heap property by performing a sift-down operation.
     - `_siftUp(index)`: Internal method used by `insert()`. Performs the sift-up operation to restore the heap property starting from the given index.
     - `_siftDown(index)`: Internal method used by `popMax()`. Performs the sift-down operation to restore the heap property starting from the given index.
     - `_getMaxChild(index)`: Internal method used by `_siftDown()`. Finds the index of the maximum child of the element at the given index.
   
   Overall, this class implements a max heap data structure with a branching factor of `x`. It allows for efficient insertion and removal of elements, ensuring that the maximum element is always at the root of the heap.

2. `DatabaseConnector`:
   - This class manages a connection to a SQLite database and provides methods to populate the database with data imported from spreadsheets.
   - The class has the following methods:
     - `__init__(self, database_file)`: Initializes the class by creating a connection to the specified SQLite database file and setting up a cursor to execute SQL queries.
     - `populate(self, spreadsheet_folder)`: Populates the database with data imported from spreadsheets located in the specified folder.
     - `populate_first_shipping_data(self, csv_reader_0)`: Populates the database with data imported from the first spreadsheet (shipping_data_0.csv).
     - `populate_second_shipping_data(self, csv_reader_1, csv_reader_2)`: Populates the database with data imported from the second (shipping_data_1.csv) and third (shipping_data_2.csv) spreadsheets.
     - `insert_product_if_it_does_not_already_exist(self, product_name)`: Inserts a new product into the database if it does not already exist.
     - `insert_shipment(self, product_name, product_quantity, origin, destination)`: Inserts a new shipment into the database.
     - `close(self)`: Closes the database connection.
   
   The `populate()` method is the entry point for populating the database. It reads data from three different CSV files and uses the other methods to insert the data into the appropriate tables in the database. It also handles the logic to ensure that existing products are not duplicated in the product table.

Overall, the `DatabaseConnector` class provides a way to populate a SQLite database with data from spreadsheets, while the `PowerOfTwoMaxHeap` class implements a max heap data structure. These classes serve different purposes and can be used independently based on their intended functionalities.
