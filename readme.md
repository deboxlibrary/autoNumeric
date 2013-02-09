# autoNumeric-1.8.2

Is a jQuery plugin that automatically formats currency and numbers as you type on form inputs. It supports most International numeric formats and currency signs including those used in Europe, North and South America, Asia and India lakhs (Lakhs values supported below 1 billion). 

Any number of currency formats can reside on the same page and are configured by settings/options that can be placed as HTML5 data attribute or passed as an argument. These settings can easily be changed at any time using the new �update� method or via the callback feature. autoNumeric to many other elements, allowing you to place formatted numbers and currency on just about any part of the page.

Seven built in methods gives you the flexibility needed to use autoNumeric to its maximum potential. You can now easily start and stop autoNumeric, update the settings and remove the formatting from multiple inputs, preparing the values for manipulation or form submission.

There are fifteen settings/options which controls the behavior and format of the form input field. These options are easy to implement with the data/argument code generator located below.

If you are developing sites that span across International lines that use different currency symbols and formats you will find autoNumeric the ideal tool to shorten your development time.

****

The following is a list of the methods and settings/options the control autoNumeric - please my home page for a complete demo and documentation [http://www.decorplanit.com/plugin/](http://www.decorplanit.com/plugin/)

****

###  Methods that are supported:
    
**init** - $(selector).autoNumeric('init', {options}); - *initializes autoNumeric*

**destroy** - $(selector).autoNumeric('destroy'); - *stops autoNumeric*

**update** - $(selector).autoNumeric('update', {options}); - *updates autoNumeric's settings*

**set** - $(selector).autoNumeric('set', value); - *returns a formatted string via jQuery's ".val()" or ".text' methods to the selected tag(s)*

**get** - $(selector).autoNumeric('get'); - *allows you to easily remove the formatting from a string on a autoNumeric controlled element and returns a value*

**getString** - $(selector).autoNumeric('getString'); - *this basically uses jQuery's .serialize() method which creates a text string (URL-encoded notation) from a set of form elements that is ready for submission. The extra step taken here is the string is split and iterated through and the formatted values are replaced with unformatted values. The string is then joined back together and returned*

**getArray** - $(selector).autoNumeric('getArray'); - *this basically uses jQuery's .serializeArray() method which returns a Javascript array of objects, ready to be encoded as a JSON string*

**getSettings** - $(selector).autoNumeric('getSettings'); - *this returns an object that shows the autoNumeric settings for the field. You may find this helpful when developing a page*

****

###  Settings / options that are supported: 
[visit my home page for an easy to use settings and option code generator ](http://www.decorplanit.com/plugin/)

**"aSep"** - controls the thousand character

+	aSep: ','	comma (default)
+	aSep: '\''	apostrophe (note: the apostrophe is escaped)
+	aSep: '.'	period
+	aSep: ' '	space
+	aSep: ''	none

**"dGroup"** - controls the digital grouping and the placement of the thousand separator

+	dGroup: '3'	 produces 333,333,333   (default)
+	dGroup: '2'	 produces 22,22,22,333 (India's lakhs format on values below 1 billion)
+	dGroup: '4'	 produces 4,4444,4444 used in some Asian country's

**"aDec"** - controls the decmial character

+	aDec: '.'	period   (default)
+	aDec: ','	comma

**"altDec"** - this was developed to accommodate for different keyboard layouts. altDec allows you to declare an alternative key to enter the decimal separator assigned in aDec

+	altDec: null   (default)

**"aSign"** - displays the desired currency symbol (examples: � or EUR). Note: other symbols can be used, such as %, �C, �F, km/h & MPH the possibilities are endless

+	aSign: '' none   (default)

**"pSign"** - controls the placement of the currency symbol (prefix or suffix)

+	pSign: 'p' prefix to the left   (default)

**"vMin"** - controls the minimum value allowed

+	vMin: '0.00'   (default)

**"vMax"** - controls the maximum value allowed

+	vMax: '999999999.99'   (default)

*Note - setting the vMin and vMax to both positive or negative with situations that limits the users ability to enter the proper values*  

**"mDec"** - overrides the decimal places that that are set via the vMin/vMax values

+ 	mDec: null   (default method)

**"mRound"** - sets the rounding method used (9 different available)

+ 	mRound: 'S'	Round-Half-Up Symmetric   (default)
+ 	mRound: 'A'	Round-Half-Up Asymmetric
+ 	mRound: 's'	Round-Half-Down Symmetric (lower case s)
+ 	mRound: 'a'	Round-Half-Down Asymmetric (lower case a)
+ 	mRound: 'B'	Round-Half-Even "Bankers Rounding"
+ 	mRound: 'U'	Round Up "Round-Away-From-Zero"
+ 	mRound: 'D'	Round Down "Round-Toward-Zero" - same as truncate
+ 	mRound: 'C'	Round to Ceiling "Toward Positive Infinity"
+ 	mRound: 'F'	Round to Floor "Toward Negative Infinity"

**"aPad"** - controls padding of the decimal places

+ aPad: true	always pads the decimal with zeros (default)

**"nBracket"** - controls if negative values are display with brackets when the input does not have focus

+	nBracket:null	 no brackets use for negative values (default)

**"wEmpty"** - controls input display behavior

+	wEmpty: 'empty'	allows input to be empty   (default)
+	wEmpty: 'zero'	input field will have at least a zero value
+	wEmpty: 'sign'	the currency symbol is always present

**"lZero"** - controls leading zeros behavior

+	lZero: 'allow'	allows leading zero to be entered. They are removed on focusout event (default)
+	lZero: 'deny'	leading zeros not allowed.
+	lZero: 'keep'	leading zeros allowed and will be retained on the focusout event

**"aForm"** - controls if default values are formatted on page ready (load)

+	aForm: true	default values are formatted on page ready (default)
+	aForm: false	default values are NOT formatted on page ready

****

**Changing the defaults via options**
  
You can change the defaults with options via the "init" method or the "update" method after autoNUmeric has been initialized - example:

&lt;input type="text" id="someID" class="someClass"&gt;

$('#someId').autoNumeric('**init**', {aSign: '� ', vMax: '-999999999.99', nBracket: '()'});

+ Initializes autoNumeric 
+ Adds the Euro sign
+ Allows negative value of -999999999.99
+ Allows brackets on negative values

**Changing the defaults via HTML5 data attribute**
  
You can also change the defaults with HTML5 data attributes - example:


&lt;input type="text" id="someID" class="someClass  data-a-sign="� " data-v-max="-999999999.99" data-n-bracket"()"&gt;

$('#someId').autoNumeric('**init**');

+ Initializes autoNumeric 
+ Adds the Euro sign
+ Allows negative value of -999999999.99
+ Allows brackets on negative values

*Note: By convention the data attribute is written in lowercase. Compound words (example: "aDec") need to be split and separated by a dash. The equal sign separates the name and value. The value should be enclosed with quote marks. If multiple options are being used they each need to have the own data attribute.*


 