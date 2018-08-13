# csvtojson

<h2>Overview</h2>

The program csv_to_json.py was used to take a spreadsheet of student grades and turn them into a more readable json file, scores.py.  This allowed for the students to search through the json file for their secret ID and find specific grades more easily than having to follow columns down in the csv.

<img src="https://i.imgur.com/8w2Bisp.png"></img>

This is how the spreadsheet looked originally, although there are many more rows not captured in the screenshot.  When viewed at a regular viewing size, many rows and columns are cut off, making it difficult to see which rows apply to which secret ID and what each value in a column applies to.  I put each secret ID's scores into a json file for easy searching and viewing of the graded portions.

<img src="https://i.imgur.com/xwYr9YM.png" width="400"></img>

Each secret ID was arranged as such, so that each score was with its appropriate column value, increasing readability.

Also included is the program find_user.py that will find your ID when it is given and print out only your scores, as opposed to using ctrl f to find your scores.

<hr>

<h2>How it Works</h2>

The program works by reading the csv then creating the base json that each student object will be loaded into.  Each student object is a python dictionary that is updated in each nested loop when looping through the table.  Once the nested loop executes completely, it is added to the "students" section of the json_out value.  In the nested loop, each column name is paired with the matching value for the certain student using the values obtained from iterrows().  Unnecessary portions of the column name are removed, and the values are added to the student's dictionary, which is then added to the json string.

Once this is completed, the json string is then dumped to a file.
