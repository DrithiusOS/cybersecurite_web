Solutions pour les missions

Mission 1:
Faire une injection SQL:  "' OR 1+1; # "

Mission2:
Parer les injections SQL en modifiant les requêtes SQL:
  $query = "INSERT INTO user (email, password) VALUES (?, ?)";
$stmt = $conn->prepare($query);

$stmt->bind_param("ss", $email, $password);

if ($stmt->execute()) {
    echo "Utilisateur inséré avec succès.";
} else {
    echo "Erreur lors de l'insertion de l'utilisateur : " . $stmt->error;
}
