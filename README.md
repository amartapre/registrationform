  <?php include("connection.php");?>

 <!DOCTYPE html>
 <html>
 <head>
 	<meta charset="utf-8">
 	<meta name="viewport" content="width=initial-scale=1">
 	<link rel="stylesheet" type="text/css" href="style.css">
 	<title>Student  registration </title>

 </head>
 <body>
 
<div class="container">
	<form action="#" method="POST">
	<div class="title">
		Student Registration Form
	</div>
    
    <div class="form">
 	<div class="input_field">
		<label>First Name</label>
		<input type="text" class="input"name="fname" required>
	</div>

  <div class="input_field">
		<label>Last Name</label>
		<input type="text" class="input"name="lname"required>
	</div>

	<div class="input_field">
		<label for="exampleInputpassword1">Password</label>
		<input type="Password" class="input" name="pass"required>
	</div>

	<div class="input_field">
		<label for="exampleInputpassword1"> Confirm Password</label>
		<input type="Password" class="input"  name="conpassword"required>
	</div>

	<div class="input_field">
		<label>Gender</label>
		<div class="custom_select">
		<select name="gender"required>
			<option value="">Select</option>
			<option value="Male">Male</option>
			<option value="Female">Female</option>
		</select>
	</div>
	</div>

	<div class="input_field">
		<label>Email id</label>
		<input type="text" class="input"name="email"required>
	</div>

	<div class="input_field">
		<label>Phone Number</label>
		<input type="text" class="input"name="Phone"required>
	</div>

	<div class="input_field">
		<label>Address</label>
		<textarea class="textarea"name="Address"required></textarea>
	</div>

	<div class="input_field terms">
		<label class="check">
		<input type="checkbox"required>	
		<span class="checkmark"></span>
       </label>
		<p>Agree to terms and conditions </p>
	</div>

  <div class="input_field">
    <input type="submit" value="submit" class="btn"name="sub">
   </div>
   <p >Amar</p> 

</div>
</form>
</div>

 </body>
 </html>

 <?php
 error_reporting(0);
  if($_POST['sub'])
  {
  	$fname=$_POST['fname'];
  	$lname=$_POST['lname'];
  	$password=$_POST['pass'];
  	$Confirmpassword=$_POST['conpassword'];
  	$gender=$_POST['gender'];
  	$email=$_POST['email'];
  	$Phone=$_POST['Phone'];
  	$Address=$_POST['Address'];

  	 
   
  	$query="INSERT INTO form values ('$fname','$lname','$password','$Confirmpassword','$gender','$email','$Phone','$Address')";
  	$data = mysqli_query($conn,$query);    
  
   if($data)
    {
 	 // echo "data inserted into database";
    }
   else
    {
    	echo "failed";
    }

 

 
  }
 ?>
 
 *
{
    padding: 0;
    margin: 0;
    box-sizing: border-box;

}
body
{

    background-color: rgba(245, 10, 175, 0.669);
    padding: 0 10px;
}
.container
{
    border: 1px solid black;
    max-width: 500px;
    width: 100%;
    background-color: white;
    margin: 20px auto;
    padding: 30px;
    box-shadow: 5px 5px 5px rgba(0,0,0,0.5);
}
.container .title
{
    font-size: 24px;
    font-weight: 700;
    margin-bottom: 25px;
    color: rgba(245, 10, 175, 0.669);
    text-align: center;
}
.container  .form  .input_field
{
    margin-bottom: 15px;
    display: flex;
    align-items: center;
}
 .container .form .input_field label
 {
    width: 200px;
    margin-right:10px;
    font-size: 14px;
 }
  .container .form .input_field .input ,
  .container .form .input_field .textarea 
  {
  width: 100%;
  outline: none;
  border: 1px solid rgba(245, 10, 175, 0.669);
  font-size: 15px;
  padding: 8px 10px;
  border-radius: 3px;
  transition: all 0.5s ease;

  }
 .container .form .input_field .textarea
 {
 resize: none;
 height: 70px;

 }
 .container .form .input_field .custom_select
 {
    position: relative;
    width: 100%;
    height: 37px;
 }
 .container .form .input_field .custom_select select
{
-webkit-appearance: none;
appearance: none;
width: 100%;
height: 100%;
padding: 8px 10px;
border: 1px solid rgba(245, 10, 175, 0.669);
border-radius: 3px;
outline: none;
}
.container .form .input_field .custom_select:before
{

content: "";
position: absolute;
top: 12px;
right: 10px;
border: 8px solid black;
border-color:rgba(245, 10, 175, 0.669) transparent transparent transparent;
pointer-events: none;

}
.container .form .input_field .input:focus,
.container .form .input_field .textarea :focus ,
.container .form .input_field select :focus
{
    border:1px solid purple;
}
.container .form .input_field p
{
    font-size: 14px;
    color: #757575;
}
.container .form .input_field  .check
{
    width: 15px;
    height: 15px;
    position: relative;
    display: block;
    cursor: pointer;
}
.container .form .input_field  .check input [type="checkbox"]
{
    position: absolute;
    top: 0;
    left: 0;
    opacity: 0;
}
.container .form .input_field  .check .checkmark
{
    width: 15px;
    height: 15px;
    /*border: 1px solid rgba(245, 10, 175, 0.669);*/
    display: block;
    position: relative;
}
/*.container .form .input_field  .check .checkmark:before
{

    position: absolute;
    top: 1px;
    left: 2px;
    width: 5px;
    height: 2px;
    border: 2px solid;
    border-color: transparent transparent white white;
    transform: rotate(-45deg);
}*/
.container .form .input_field  .check input [type="checkbox"]:checked ~  .checkmark
{
    background:red;
}
.container .form .input_field .btn
{
    width: 100%;
    padding: 8px 10px ;
    font-size: 15px;
    border: 0px;
    background:rgba(245, 10, 175, 0.669);
    cursor: pointer;
    border-radius: 3px;
    outline: none;
}
.container .form .input_field:last-child
{
    margin: bottom:0;
}
.container .form .input_field .btn:hover
{
    background-color: purple;
}
@media (max-width: 420px)
{
.container  .form  .input_field
{
    flex-direction: column;
    align-items: flex-start;
}
.container  .form  .input_field label
{
    margin-bottom: 5px;
}
.container  .form  .input_field .terms
{
    flex-direction: row;
}

 <?php
 $servername = "localhost";
 $username="root";
 $password="";
 $dbname= "responsive";
 
 $conn = mysqli_connect($servername,$username,$password,$dbname);
 
 if($conn)
 {
	 //echo "connection ok";
 }
 else
 {
	 echo "connection failed";
 }
 ?>
