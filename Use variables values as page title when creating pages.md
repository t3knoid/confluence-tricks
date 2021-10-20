# Use variables values as page title when creating pages
This trick uses a bit of Javascript inside the HTML macro in a template.

The first thing to do is to create a template containing variables to use as a page title. These variables can be of any type, text, multi-line text, and a list. It is important to note this now because it affects the Javacript code.

Insert the HTML macro at the end of the template and add the following code snipped:

    # Use variables values as page title when creating pages
This trick uses a bit of Javascript inside the HTML macro in a template.

The first thing to do is to create a template containing variables to use as a page title. These variables can be of any type, text, multi-line text, and a list. It is important to note this now because it affects the Javacript code.

Insert the HTML macro at the end of the template and add the following code snipped:

    <script>
	    var varSelect, varMultiline, varText;
    
	    $("textarea[name='variableValues.varSelect']").change(function() {
		    var1=$("select[name='variableValues.varSelect']").val();
	        var2=$("textarea[name='variableValues.varMultiline']").val();
	        var3=$("text[name='variableValues.varText']").val();
	        console.log(user+functionality+goal);
	        $("form[name='filltemplateform']").find("input[name='title']").val("Var1 " + var1 + ", Var2 " + var2 + ", Var3 " + var3)
	        })
    </script>

Each template variable value is captured in a script variable (e.g. var1) using jquery. In this example, the statement returns the value of the varSelect template variable which happens to be a select element.

    var1=$("select[name='variableValues.varSelect']").val()

A multi-line variable is a textarea element and will have the following jquery statement:

    var2=$("textarea[name='variableValues.varMultiline']").val();

A single text variable is a text element and will have the following jquery statement:

    var3=$("text[name='variableValues.varText']").val();

Note that this script only works if the user actually changes the value of the *varSelect* variable during data entry controlled by the following:

    .change(function()
