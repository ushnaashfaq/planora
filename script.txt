// =======================
// MOTIVATION QUOTES
// =======================

const quotes = [
    "Small steps every day lead to big success.",
    "Discipline beats motivation when motivation fades.",
    "Study now, shine later.",
    "Consistency creates confidence.",
    "Focus on progress, not perfection.",
    "Your future self will thank you."
];

function newQuote() {
    const quoteElement = document.getElementById("quote");
    if (!quoteElement) return;

    const randomIndex = Math.floor(Math.random() * quotes.length);
    quoteElement.innerText = quotes[randomIndex];
}

// =======================
// CURRICULUM BUILDER
// =======================

function addSubject() {
    alert("Subject added successfully!");
}

function generatePlanner() {
    alert("Planner generated!");
}

// =======================
// WEEKLY PLANNER
// =======================

function addSession() {
    alert("Study session added!");
}

// =======================
// QUIZ LOGIC
// =======================

function checkAnswer(answer) {
    const result = document.getElementById("quizResult");
    if (!result) return;

    if (answer === "Paris") {
        result.innerText = "✅ Correct! Paris is the capital of France.";
        result.style.color = "green";
    } else {
        result.innerText = "❌ Wrong answer. Try again!";
        result.style.color = "red";
    }
}
// =======================
// EXTRA CURRICULAR ACTIVITY
// =======================

function showActivitySection(show) {
    const section = document.getElementById("activitySection");
    section.style.display = show ? "block" : "none";
}

function previewMedia() {
    const fileInput = document.getElementById("activityMedia");
    const preview = document.getElementById("mediaPreview");
    preview.innerHTML = "";

    const file = fileInput.files[0];
    if (!file) return;

    const fileURL = URL.createObjectURL(file);

    if (file.type.startsWith("image")) {
        const img = document.createElement("img");
        img.src = fileURL;
        img.style.maxWidth = "200px";
        img.style.marginTop = "10px";
        preview.appendChild(img);
    } 
    else if (file.type.startsWith("video")) {
        const video = document.createElement("video");
        video.src = fileURL;
        video.controls = true;
        video.style.maxWidth = "250px";
        video.style.marginTop = "10px";
        preview.appendChild(video);
    }
}


// =======================
// SAFE PAGE LOAD (NO CONFLICTS)
// =======================

document.addEventListener("DOMContentLoaded", function () {
    newQuote(); // will only run if #quote exists
});