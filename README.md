# Notes50

#### A CS50 Notes And PSets Reader.

#### Video Demo: https://www.youtube.com/watch?v=wtuPx1vHtjo

### Arguments
    -x : CS50X
    -p : CS50 Python
    -w : CS50 Web
    -g : CS50 Games
    -a : CS50 Ai

### Syntax
    -Argument Week: Week For Which Notes To Read 
    -Argument Week/PSets: Week For Which PSets To Read

### Examples
    To Get CS50X Week 0 Notes
    - python notes50.py -x 0

    To Get CS50X Week 0 Pset Scratch
    - python notes50.py -x 0/scratch


## Programming
    Notes50 Is Written In Python
    With A Mix Of Multiple Pip Libraries Which You Can Find In Requirements.Txt

    Some Of The Important Libraries Are:
        - Argparse: 
            I Used Argparse To Add Arguments Of Courses And Help Function 
        - Urllib:
            I Used Urllib Function Request To Get The Html File From The CS50 Website
            At First I Used Requests Library But It Had A Weird Problem When Encountered
            With Smart Quotes Causing It To Display Weird Symbol Thats Why I Then Changed It To Urllib
        - Beautifulsoup: 
            After Urllib Gets The Website Source Code I Used Beautifulsoup To Parse It 
            It Turns The Html Tags To Be Programmable And Understandable To Other Libraries 
            Like Markdownify And I Used Lxml To Parse The Html.
        - Markdownify:
            Rich Has A Markdown Library That Parses Markdown The Way It Was Intended And Prints It To The Terminal 
            That'S Why I Needed A Html To Markdown Library So I Searched A Little And Used Markdownify.
        - Rich: 
            Rich Has A Markdown Function That Prints Markdwon To The Terminal 
            And Some Syntax Highliting That'S Why I Used It To Print Markdown

### Functions
    These Are The Functions That I Have
        - Parse_Args:
            Parse_Args Is A Function That Uses Argparse And Adds Arguments 
            Such As The Course Flags And The Help Flags And Parses It 
            And Then Returns It To The Main Function.
        - Help:
            Help Function Makes A Examples Text And Returns It To Argparse To Use It.
        - Note: 
            A Kind Of A Url Parser That Turns And Add The Given Input To CS50 Courses Notes Url 
            And Then Passes It To The Get Function. 
        - PSet: 
            Just Like Note Function Pset Also Parses The Given Input 
            And Adds It To PSets Url Of CS50 Courses And Then Passes It To The Get Function.
        - Get: 
            Get Function Gets The Given Arguments Url Source Code Using Urllib Library 
            Then That Source Code Is Passed To Beautifulsoup And It Parses Using Lxml To Pretty Html And
            Then Gets Its Main Tag Text Which Is Passed To Markdownify Function 
            That Turns It To Markdown Which Again Is Passed To Rich Function 
            That Turns The Markdown To Actual Markdown And Then Return That To The Calling Function 
            And It Is Printed To The Terminal By The Main Function.

### Caching
    I Used Joblib To Cache The Results As Getting The Html Causes Some Delay
    So By Using Caching It Can Return Previously Used Results Without Any Wasted Time
    It Uses Appdirs To Get The User Cache Directory
    The First Time Maybe Slow But From The Second Time 
    It Will Be Fast As It Will Cache The First Results.
