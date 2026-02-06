<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Will You Be My Valentine?</title>

<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Nunito:wght@200..900&family=Poppins:wght@100..900&display=swap" rel="stylesheet">

<style>
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
    background-color: white;
    font-family: "Nunito", sans-serif;
    flex-direction: column;
}

/* Main Container */
.container {
    text-align: center;
}

/* Heading */
h1 {
    font-size: 2.5em;
    color: #d32f2f;
}

/* Buttons */
.buttons {
    margin-top: 20px;
}

.yes-button {
    font-size: 1.5em;
    padding: 10px 20px;
    margin-right: 10px;
    background-color: #fa0561;
    color: white;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

.yes-button:hover {
    background-color: #e03777;
}

.no-button {
    font-size: 1.5em;
    padding: 10px 20px;
    background-color: #d3d3d3;
    color: black;
    border: none;
    border-radius: 5px;
    cursor: pointer;
}

/* GIF */
.gif_container img {
    width: 300px;
    height: auto;
    border-radius: 10px;
    margin-top: 20px;
}

/* YES PAGE (Hidden Initially) */
#yesPage {
    display: none;
    text-align: center;
}

#yesPage h1 {
    font-size: 3em;
    color: #d32f2f;
}
</style>
</head>

<body>

<!-- FIRST PAGE -->
<div class="container" id="mainPage">
    <div class="gif_container">
        <img src="https://gifdb.com/images/high/cute-love-bear-roses-ou7zho5oosxnpo6k.gif">
    </div>

    <h1>Will you be my Valentine?</h1>

    <div class="buttons">
        <button class="yes-button" onclick="handleYesClick()">Yes</button>
        <button class="no-button" onclick="handleNoClick()">No</button>
    </div>
</div>

<!-- YES PAGE -->
<div id="yesPage">
    <h1>Knew you would say yes!</h1>

    <div class="gif_container">
        <img src="https://media.tenor.com/gUiu1zyxfzYAAAAi/bear-kiss-bear-kisses.gif">
    </div>
</div>

<script>
const messages = [
    "Are you sure?",
    "Really sure??",
    "Are you positive?",
    "Pookie please...",
    "Just think about it!",
    "If you say no, I will be really sad...",
    "I will be very sad...",
    "I will be very very very sad...",
    "Ok fine, I will stop asking...",
    "Just kidding, say yes please! ❤️"
];

let messageIndex = 0;

function handleNoClick() {
    const noButton = document.querySelector('.no-button');
    const yesButton = document.querySelector('.yes-button');

    noButton.textContent = messages[messageIndex];
    messageIndex = (messageIndex + 1) % messages.length;

    const currentSize = parseFloat(window.getComputedStyle(yesButton).fontSize);
    yesButton.style.fontSize = `${currentSize * 1.5}px`;
}

function handleYesClick() {
    document.getElementById("mainPage").style.display = "none";
    document.getElementById("yesPage").style.display = "block";
}
</script>

</body>
</html>
