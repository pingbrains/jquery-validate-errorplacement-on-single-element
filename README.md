jquery-validate-errorplacement-on-single-element
================================================

jQuery validate errorPlacement on single element

While validating form using jQuery Validate, if you need to change the error placement of one or more specific elements, then you can do this using errorPlacement option supported by jQuery validate.

Demo:
<a href="http://demo.pingbrains.com/jquery-validate-errorplacement-on-single-element/">http://demo.pingbrains.com/jquery-validate-errorplacement-on-single-element/</a>

Code:

```
	<form action="" methpd="post" id="sample-form">
		<div class="form-group">
			<lable for="firstname">First Name</lable>
			<input type="text" name="firstname" id="firstname" class="form-control">
		</div>
		<div class="form-group">
			<lable for="lastname">Last Name</lable>
			<input type="text" name="lastname" id="lastname"  class="form-control" >
		</div>
       <div class="checkbox">
       	<div>
          <label>
          	
          		<input type="checkbox" name="terms_of_use" value="">I agree to terms of use
          	
          </label>
         </div> 
        </div>			
		<div><input type="submit" class="button button-primary" value="Submit"></div>
	</form>
	
(function(){
	$("#sample-form").validate({
		rules:{
			firstname : {
				required : true
			},
			lastname : {
				required : true
			},			
			terms_of_use: {
				required : true
			}	
		},
		messages:{

		},
		errorPlacement: function(error, element) {
		if (element.attr("name") == "terms_of_use")
		    {
		        error.insertAfter(".checkbox div");
		    }
		    else
		    {
		        error.insertAfter(element);
		    }
		}		
	})
})();

```

Above code will throw the error message (for checkbox element), after the div that wraps checkbox label. 


