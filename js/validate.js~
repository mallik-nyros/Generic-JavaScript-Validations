function Validate(_f) {
				 var a=new Array();
					 for (var i=0; i<_f.elements.length; i++) {
										var element=_f.elements[i];
										var elName=element.name;
													if ((!elName)||(elName.length == 0)||(a[elName]))
													continue;
												a[elName] = true;
													var validationType = element.getAttribute("validate");
													
											if((!validationType)||(validationType.length == 0))
														continue;
							var arrValidationTypes = validationType.split("|");
								for (var j=0; j<arrValidationTypes.length; j++) {
									var n = arrValidationTypes[j];
										var blnValid=true;
											switch (n) {
											case "not_empty":
																blnValid = ValidateNotEmpty(element);
													break;
												case "email":
																	blnValid = ValidateEmail(element);
													break;
													
												
												case "phone":
																blnValid = ValidatePhone(element);
														break;
										}

			if (blnValid == false) {
						var message="Enter the value of "+element.name;
							alert(message);
									if ((typeof element.focus == "function")||(element.focus)) {
											element.focus();
							}
							
							return false;
						}
			
				}
			 }
  return true;
}

function GetElementValue(objElement) {
 var result="";
 			switch (objElement.type) {
			case "text":
			case "password":
						result = objElement.value;
			break;
				
				case "select":
								
					     result= objElement.Index.value
					break;
					case "radio":
					case "checkbox":
								for (var i=0; i<objElement.form.elements.length; i++) {
										if (objElement.form.elements[i].name == objElement.name) {
										if (objElement.form.elements[i].checked)
											result += objElement.form.elements[i].value+",";

												}
											}
											break;
						 }
			 return result;
				}


//Empty Validation

function ValidateNotEmpty(objElement) {

 var strValue = GetElementValue(objElement);

 var blnResult = true;

 if((strValue) == "") //check for nothing
 {
	 blnResult = false;
 }
	 return blnResult;
}


//Email Validation
function ValidateEmail(objElement) {

var x=GetElementValue(objElement);
var atpos=x.indexOf("@");
var dotpos=x.lastIndexOf(".");
if (atpos<1 || dotpos<atpos+2 || dotpos+2>=x.length)
  {
   return false;
	}
}
 
 
 //Valid PhoneNumber
 function ValidatePhone(b){
  var a = "0123456789";
        var d = b.value;
        var e;
        var c = true;
        if (d.length <=9) {
            return false;
        }
        for (i = 0; i < d.length && c == true; i++) {
            e = d.charAt(i);
            if (a.indexOf(e) == -1) {
                alert("Please enter only numeric value...");
        
            b.select();
            c = false;
        }
    }
 }






