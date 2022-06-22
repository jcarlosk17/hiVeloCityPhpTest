# Simple code challenge #

Here I opted to make some changes based on my way of working and my current knowledge:
1. Using the function file(), instead fopen()
	Getting all the information at once and work with the content from an array instead of keep the file opened and read it line by line.

2. Using array_map() and str_getcsv()
	To get each element separated by commas from each element (line from CSV) returned by file().

3. Using Lists and array_shift()
	On this example is expected that first line from the CSV contains needed information for the final result, being in a different format from the remaining lines. Each element is being associated on the respective variable and the first line is removed from the main array, leaving only the records of transactions.

4. Looping on the records
	Executing on all elements remained on the array, once reading the inner element verifies if the line has at least 12 elements, since the highest we will be working with is the 12th. In case of a blank line on the CSV file or simply less than the required 12 elements, this transacation will be skipped. In case of having a blank element, will be treated as a normal line and the expected process and result.

5. Parsing only to int (subunits)
	I saw as unecessary parsing the number as float and later parsing as int, since we will multiply it for 100 as our expected result.

6. Assigning directly to the array ($rcs)
	Instead of using an auxiliary variable ($rcd), can be assigned directly to our array $rcs.

7. Remove of the array_filter()
	Since we are checking if each line has more than 12 elements (between commas) there is no risk of having a complete empty element on our array.

8. Remove of the returned array element "document".
	Since this element is not expected to be on the final result, it was removed. 