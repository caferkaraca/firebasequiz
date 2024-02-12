<?php
require_once 'config.php';
require_once 'firebaseRDB.php';

if (session_status() == PHP_SESSION_NONE) {
    session_start();
}

$firebase = new firebaseRDB($databaseURL);
$questionsData = $firebase->retrieve("questions");
$questions = json_decode($questionsData, true);

$message = '';

if ($_SERVER["REQUEST_METHOD"] == "POST") {
    $questionId = $_SESSION['question_id'];

    // Yeni kod parçası
    $question = null;
    foreach ($questions as $unit) {
        if (isset($unit[$questionId])) {
            $question = $unit[$questionId];
            break;
        }
    }

    if ($question !== null) {
        $solution = $question["solution"];
        $answer = $_POST["answer"];

        if ($answer == $solution) {
            $message = '<div class="alert alert-success">Doğru cevap!</div>';
        } else {
            $message = '<div class="alert alert-danger">Yanlış cevap:'. $answer.' <p class="text-success"> Doğru cevap: ' . $solution . '</p></div>';
        }
    } else {
        $message = '<div class="alert alert-danger">Hata: Doğru soru bulunamadı!</div>';
    }
}

$randomQuestionUnit = array_rand($questions);
$randomQuestionId = null;
if ($randomQuestionUnit !== false && isset($questions[$randomQuestionUnit])) {
    $randomQuestionId = array_rand($questions[$randomQuestionUnit]);
}
if ($randomQuestionId !== null) {
    $_SESSION['question_id'] = $randomQuestionId;
    $randomQuestion = $questions[$randomQuestionUnit][$randomQuestionId]["question"];
} else {
    $message = '<div class="alert alert-danger">Hata: Doğru soru bulunamadı!</div>';
}
?>
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Soru Çözme Uygulaması</title>
    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
    <style>
        body {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }

        .container {
            text-align: center;
        }
    </style>
</head>

<body>
    <div class="container">
        <h2>Soru Çözme Uygulaması</h2>
        <div class="row justify-content-center">
            <div class="col-md-6">
                <?php if (isset($randomQuestion)) { ?>
                    <p><?php echo $randomQuestion; ?></p>
                    <form action="" method="POST">
                        <div class="form-group">
                            <input type="text" class="form-control" id="answer" name="answer" placeholder="Cevabınızı girin">
                        </div>
                        <button type="submit" class="btn btn-primary">Gönder</button>
                    </form>
                <?php } ?>
                <!-- Modal -->
                <div class="modal fade" id="messageModal" tabindex="-1" role="dialog" aria-labelledby="messageModalLabel" aria-hidden="true">
                    <div class="modal-dialog modal-dialog-centered" role="document">
                        <div class="modal-content">
  
                            <div class="modal-body text-center">
                                <?php echo $message; ?>
                            </div>
                           
                                <button type="button" class="btn btn-secondary" data-dismiss="modal">Devam Et</button>
                         
                        </div>
                    </div>
                </div>
                <!-- /Modal -->

            </div>
        </div>
    </div>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
    <script>
        // Modal gösterme işlemi
        <?php if ($message) { ?>
            $('#messageModal').modal('show');
        <?php } ?>
    </script>
</body>

</html>
