### Hi there 👋

<!--
**jorgenino911/jorgenino911** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

<?php
include('connection.php');
$con=connection();
$sql= "SELECT * FROM user";
$query = mysqli_query($con, $sql);
?>

<!DOCTYPE html>
<html>
<head>
	<title> Pagina Mascotas</title>
	<link rel="stylesheet" type="text/css" href="webMascota.css">
</head>
<body>
	
	<section class="estilo">
	<!-- <h1 style="text-align: center; "> Agendar cita de tú mascota</h1> -->
	<div class="usurio">
	
		<h3>DATOS DE USUARIO</h3>
		<img src="avatar.jpg"alt="avatar"Height="120" wide="120">
<tbody>

		<form action=" inser_User.php" method="POST">
			<h1> Crear usuario</h1>
			<input type="number" name="docuemto"placeholder="Documento de indentidad" required="docuemto"autofocus  ><br>
			<input type="texto" name="nombre"placeholder="Nombre"required="nombre"><br>
			<input type="number" name="telefono"placeholder="Telefono"required="telefono"><br>
			<input type="email" name="correo"placeholder="Correo electronico"><br>
			<input type="submit" value =" Agregar usuario">
			<!-- <input type="submit" value =" Cancelar"> -->
		</form>

	</div>
	<div >
		<h2>Usuario registrado</h2>
		<table>
			<style > 
      		table, td,th
      		{
					border: 2px solid black;
					border-collapse: collapse;
			}
      	</style>
			<thead></thead>
				<tr>
					<th>ID</th>
				<th> Documento de identidad</th>
				<th>Nombre y apellido</th>
				<th>Telefono</th>
				<th>Correo</th>
				<th></th>
				<th></th>
				</tr>

			<tbody>
				
				
				<?php while($row = mysqli_fetch_array($query)):  ?>
				<tr>
					<th> <?= $row['ID'] ?></th>
						
					<th> <?= $row['Nombre'] ?></th>
					<th> <?= $row['Telefono'] ?></th>
					<th> <?= $row['Correo'] ?></th>
					<th>  <a href="">Editar</a></th> <br>
					<th> <a href="">eliminar</a></th>
				</tr>
				<?php endwhile; ?>
			</tbody>
		</table>
	</div>
			
	<div class="mascota">
		<h3>DATOS DE MASCOTA</h3> 
		<img src="mascota.jpg"alt="avatar"Height="120" wide="120">
		<form>
			<input type="number" name="placa" placeholder="Placa de mascota"required=""><br>
			<input type="texto" name="nombre" placeholder="Nombre de mascota"required=""><br>
			<select name="select">
				
				<option value="value" selected>Elige tu mascota</option>
			  <option value="value1">Perro</option>
			  <option value="value2" >Gato</option>
			  <option value="value3">conejo</option>
			  <option value="value3">Caballo</option>
			</select><br>
			<input type="submit" value =" Enviar">
			<input type="submit" value =" Cancelar">
		</form>
	</div>
	<div style="color: red">
		<form>
			<h3> CONFIRMAR FECHA Y HORA </h3>
			<input type="date" name="fecha">
			<input type="time" name="hora" >
			<input type="submit" name="agendar cita"> <br> <br>
		</form>
	</div>
	</section>
</body>
</html>
................................................................
<?php
include('connection.php');
$con=connection();

$id = null;

// $name = $_POST['name'];
$Nombre_y_apellido=$_POST['Nombre_y_apellido'];
$Telefono=$_POST['Telefono'];
// $password=$_POST['password'];
$Correo=$_POST['Correo'];
$sql = "INSERT INTO user VALUES ('$id',  '$Nombre', '$Telefono', 'Correo')";
$query =mysqli_query($con, $sql);

if ($query)
{
	header("Location: primeraprueba.php");
};

?>//'$name', '$password',
...........................................................
<?php
	function connection()
	{
		$host="localhost";
		$user="root";
		// $pass="";
		$bd = "user_crud_php";
		$connect = mysqli_connect($host, $user/*,$pass*/);
		mysqli_select_db($connect, $bd);
		return $connect;
	};

?>
................................................

.usurio
{
	color: red;
}

.mascota
{
	color: red;

}
.fecha
{
	color: red;
}

.estilo
{

text-align: center;
}
section
{
	
	
display: block;
border:50px solid black;
width:60%;
padding:1px;
margin:180px;
border-radius: 10px;

}
.bordo
{
	border: solid 12px black; 
}
