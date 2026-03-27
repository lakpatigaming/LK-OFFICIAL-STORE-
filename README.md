<!DOCTYPE html>
<html>
<head>
  <title>LK Official Store</title>
</head>
<body>
  <h1>Game Top-Up</h1>

  <form action="order.php" method="POST">
    <input type="text" name="userid" placeholder="User ID" required><br>
    <input type="text" name="server" placeholder="Server ID" required><br>

    <select name="package">
      <option value="86">86 Diamonds - ₹80</option>
      <option value="172">172 Diamonds - ₹150</option>
      <option value="weekly">Weekly Pass - ₹135</option>
    </select><br>

    <button type="submit">Buy Now</button>
  </form>
</body>
</html>

<?php
$userid = $_POST['userid'];
$server = $_POST['server'];
$package = $_POST['package'];

// Save order
$conn = new mysqli("localhost", "root", "", "topup");

$sql = "INSERT INTO orders(userid, server, package)
VALUES ('$userid','$server','$package')";
$conn->query($sql);

echo "Order Placed Successfully!";
?>
