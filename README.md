# alinabooo.github.io

<!DOCTYPE html>
<html>
<head>
	<link rel="stylesheet" href="https://s.pageclip.co/v1/pageclip.css" media="screen">
	<title> HTML Forms </title>
	<!-- to link with the css file -->
	<link rel="stylesheet" type="text/css" href="Quinones2.css">
	<script>
		function showdata() {
			//accesses the respective id numbers and their value and prints it out
			var custname = document.getElementById("name").value;
			var number = document.getElementById("number").value;
			var email = document.getElementById("email").value;
			var flavor = document.getElementById("flavorlist").value;

			if (document.getElementById('small').checked) {
				var size = document.getElementById('small').value;
			}

			if (document.getElementById('medium').checked) {
				var size = document.getElementById('medium').value;
			}

			if (document.getElementById('large').checked) {
				var size = document.getElementById('large').value;
			}

			var toppings = " "
			if (document.getElementById('onion').checked) {
				var toppings = toppings + document.getElementById('onion').value + " ";
			}

			if (document.getElementById('bacon').checked) {
				var toppings = toppings + document.getElementById('bacon').value + " ";
			}

			if (document.getElementById('cheese').checked) {
				var toppings = toppings + document.getElementById('cheese').value + " ";
			}

			if (document.getElementById('mushroom').checked) {
				var toppings = toppings + document.getElementById('mushroom').value + " ";
			}

			var date = document.getElementById("date").value
			var time = document.getElementById("time").value
			var address = document.getElementById("address").value

			alert("Name: " + custname);
			alert("Number: " + number);
			alert("Email: " + email);
			alert("Flavor: " + flavor);
			alert("Size: " + size);
			alert("Extra Toppings: " + toppings);
			alert("Date: " + date);
			alert("Time: " + time);
			alert("Address: " + address);
		}
		
		function checkdata() {
			//makes sure number, date, and time inputs are not empty
			if (document.getElementById("number").value == "" || document.getElementById("date").value == "" ||  document.getElementById("time").value == "") {
				alert("Inputs are incomplete!");
			}

			//makes sure the number has length of 11
			var number = document.getElementById("number").value;
			var len = number.length;
			if (len !== 11) {
				alert("Invalid mobile number format. Please follow the format 0XXX XXXX XXX.")
			}

			
			var date = document.getElementById("date").value;
		 	var current = new Date();
		 	var str_con = Date.parse(date);
		 	var str_current = Date.parse(current);
			var hour = current.getHours();

			//ensures delivery time is between 10 am to 10 pm only
    		if (hour < 10 || hour > 22){
    			alert("Delivery time must be between 10AM to 10PM only.")
    		}

			//checks if date has already passed
		 	if (str_con < str_current) {
				alert("Date has already passed.");
    		}

    		
		}

	</script>
</head>
<body>
	<h1> Order Form </h1>
	<form action="https://send.pageclip.co/wvB6mR07wuEnCMaef1PvAHe7aX4keb2H/contactform" class="pageclip-form" method="post">

		<!--name of the border, customer name, mobile num, and email add are in this first fieldset-->
		<fieldset>
			<legend>Customer Details</legend>
			<label> Customer name: <input type="text" id="name" name="cust name" required  ></label>

			<br>

			<label> Mobile number: <input type="tel" id="number" name="number"  required  ></label>

			<br>

		<!--input type "email" requires an input email-->
			<label> Email address: <input type="email" id="email" name="email"></label>
		</fieldset>

		<br>

		<!--name of the border, flavor (drop down list), size (one choice only), and toppings (can add one or more choices) are in this second fieldset-->
		<fieldset>
			<legend>Pizza Options </legend>
			<label>
				Flavor:
				<select name="flavor" id ="flavorlist">
				<option value="hawaiian">Hawaiian</option>
				<option value="double cheese">Double Cheese</option>
				<option value="marg">Margherita</option>
				<option value="bbq bac cheese">BBQ Bacon Cheeseburger</option>
				<option value="pepp chese">Pepporoni and Cheese</option>
				</select>
			</label>

			<br>

			
			<label> Size: 
				    <input type="radio" id="small" name="size" value="small"> Small </label>
			<label> <input type="radio" id="medium" name="status" value="medium"> Medium </label>
			<label> <input type="radio" id="large" name="status" value="large"> Large </label>

			<br>

			
			<label> Extra Toppings:
				   <input type="checkbox" id="bacon" name="toppings" value="bacon" > Bacon </label>
			<label><input type="checkbox" id="cheese" name="toppings" value="cheese" > Cheese </label>
			<label><input type="checkbox" id="onion" name="toppings" value="onion" > Onion </label>
			<label><input type="checkbox" id="mushroom" name="toppings" value="mushroom" > Mushroom </label>

		</fieldset>
		
		<br>
 
 		<!--name of the border, delivery date (mm.dd.yyyy), delivery time(00:00 AM/PM), and address with a large textbox input is in this third fieldset-->
		<fieldset>
			<legend> Delivery Details </legend>
			<label> Delivery date: <input type="date" id="date" name="deliv date"  required ></label>

			<br>

			<label> Preferred delivery time: <input type="time" id="time" name="pref deliv"  required ></label>

			<br>

			<label> Delivery address: <br>
				<textarea rows="5" cols="50" id="address"  required ></textarea></label>
		</fieldset>

		<br>

		<!--buttons to submit the form and reset all field to blank -->
		<button type="submit"> Submit </button>
		<button type="reset"> Reset </button>

		<button onclick="checkdata()"> Check Data </button>

		<button onclick="showdata()"> Show Data </button>

 <button type="submit" class="pageclip-form__submit">
    <span>Send</span>
  </button>
</form>
<script src="https://s.pageclip.co/v1/pageclip.js" charset="utf-8"></script>
</body>
</html>
