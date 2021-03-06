# php2html.lib
Build dynamic html pages with php functions.

Dynamic PHP to HTML generator.
If you program html output in php, you can use this library's routines to generate the html code, by calling PHP-functions.
    
ELEMENTS:
Create HTML elements INPUT / CHECKBOX / RADIO-GROUP / TABLE and other usefull, from PHP-functions.
All combined with: Label, ToolTip/Hint, Placeholder, Dimensions, Colors and more.

Included translate system. Font-awesome icons.
Extended table functions: sort, filter, zebra-stripe, fixed-header and more, with Mottie Tablesorter-system.
    
Based on PHP7+, HTML5, CSS3.
Source could be UTF-8, no tabs, indent: 4 chars

The layout is compact with labels above fields, so it is suitable to narrow screens.

All shaded labels have a tooltip/hint, that appears when mouse is held over.

Look at the xx.page.php files to see how it works.

Minimum file needs: php2html.lib.php, menu.inc.php and some in _assets folders.

Look and feel at the demo here:

<iframe width="1000px" height="800px" seamless frameborder="0" src="https://ev-soft.work/p2h/demoFile/CustomerOrder.page.php" > </iframe> 


The parameters when calling htm_Input:

    function htm_Input(
        $type='',           # text, date, ... Look at source !
        $name='',           # Set the fields name and id
        $valu='',           # The current content in input field
        $labl='',           # Translated label above the input field
        $titl='',           # Translated description about the field
        $algn='left',       # The alignment of input content (value). Default: left
        $unit='',           # A unit added to the content eg. currency or % (prefix or suffix)
        $disa=false,        # Disable the field (Output only). Default: field is active
        $rows='2',          # Number of rows in multiline input (eg. area/html) Default: 2
        $width='',          # Width of the field-container
        $step='',           # the value of stepup/stepdown for numbers
        $more='',           # Give more (special) input attrib
        $plho='@Enter...',  # Translated placeholder shown when field is empty. Default: Enter...
        $list=[]            # Data for "multi-list" (eg. options, checkbox, radiolist)
    )

For now htm_Input() has the following types:

    'date' : INPUT(type= 'date',
    'intg' : INPUT(type= 'number',
    'text' : INPUT(type= 'text',
    'dec0' : INPUT(type= 'text',        - value shown without decimals
    'dec1' : INPUT(type= 'text',        - value shown with 1 decimal
    'dec2' : INPUT(type= 'text',        - value shown with 2 decimals
    'num0' : INPUT(type= 'number',      - value shown without decimals
    'num1' : INPUT(type= 'number',      - value shown with 1 decimal
    'num2' : INPUT(type= 'number',      - value shown with 2 decimals
    'num3' : INPUT(type= 'number',      - value shown with 3 decimals
    'barc' : INPUT(type= 'text',        - value shown with barcode font
    'mail' : INPUT(type= 'email',
    'link' : INPUT(type= 'url',
    'sear' : INPUT(type= 'search',
    'file' : INPUT(type= 'file',
    'imag' : INPUT(type= 'image',
    'time' : INPUT(type= 'time',
    'rang' : INPUT(type= 'range',
    'butt' : INPUT(type= 'button',
    'colr' : INPUT(type= 'email',
    'pass' : INPUT(type= 'password',    - with strength-meter and show/hide password
    'area' : INPUT(type= 'textarea',    - (text-content)
    'html' : INPUT(type= '<div contenteditable',    - (html-content)
    'chck' : INPUT(type= 'checkbox',    - for one or multible checkboxes
    'rado' : INPUT(type= 'radio',       - for one or multible radiofields
    'opti' : INPUT(type= 'option',      - Dropdown option-list
    'hidd' : INPUT(type= 'hidden',


The parameters when calling htm_Table:

    function htm_Table(
        $TblCapt= array( # ['0:Label', '1:Width', '2:Type', '3:OutFormat', '4:horJust', '5:Tip', '6:placeholder', '7:Content';], ...
            ),
        $RowPref= array( # ['0:ColLabl', '1:ColWidth', '2:InpType', '3:OutFormat', '4:[horJust_mv]', '5:ColTip' ], ...
            ),
        $RowBody= array( # ['0:ColLabl', '1:ColWidth', '2:InpType', '3:OutFormat', '4:[horJust_mv]', '5:ColTip', '6:placeholder','7:default','8:select'], ...
            ),
        $RowSuff= array( # ['0:ColLabl', '1:ColWidth', '2:InpType', '3:OutFormat', '4:[horJust_mv]', '5:ColTip', '6:value!' ], ...
            ),
        $TblNote= '',           # HTML-string
        &$tblData,              # = array(),
        $FilterOn= true,        # Ability to hide records that do not match filter // Does not work with hidd fields!
        $SorterOn= true,        # Ability to sort records by column content
        $CreateRec=true,        # Ability to create a record
        $ModifyRec=true,        # Ability to select and change data in a row
        $ViewHeight= '400px',   # The height of the visible part of the table's data
        $CalledFrom='',         #  = '__FUNCTION__' in the subfunction (debugging)
        $Criterion= ['','']     # Test [DataKolonneNr, > grænseværdi] Undlad spec. feltColor
      ) 


To create a HTML-page use this functions:

    htm_PagePrep()                      - Prepare output to a page

    You can create:

    htm_PageBody()                      - Set body of a page

    or just write php-code to 

    echo output

    htm_PageFina()                      - Complete / finish the page
    
    
To create a Panel there are functions:

    htm_PanlHead()                      - Start top of an avanced panel

    htm_PanlFoot()                      - Finish bottom of an avanced panel



Here you will find the repository:    

https://github.com/EV-soft/ev-soft.github.io
