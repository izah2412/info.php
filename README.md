# info.php
<?php

    error_reporting(E_ALL ^ E_DEPRECATED);
	
	$host='127.0.0.1';
	$uname='root';
	$pwd='';
	$db="tuts_rest";

	$con = mysql_connect($host,$uname,$pwd) or die("connection failed");
	mysql_select_db($db,$con) or die("db selection failed");
	 
	$id=$_REQUEST['ID'];
	 
	$r=mysql_query("select * from users1 where ID='$id'",$con);

	while($row=mysql_fetch_array($r))
	{
		$flag[name]=$row[name];
	}
	 
	print(json_encode($flag));
	mysql_close($con);
?>
