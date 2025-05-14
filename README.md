# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨

@keyframes bounce {
    0%, 100% {
        transform: translateY(0);
    }
    50% {
        transform: translateY(-10px);
    }
}

.animated-button {
    padding: 10px 20px;
    font-size: 18px;
    border: none;
    background-color: #007bff;
    color: white;
    cursor: pointer;
    border-radius: 5px;
    transition: background-color 0.3s;
}

.animated-button:hover {
    animation: bounce 0.5s ease-in-out;
}

function savePreference(animationType) {
    localStorage.setItem("preferredAnimation", animationType);
}

function getPreference() {
    return localStorage.getItem("preferredAnimation") || "bounce";
}

// Example usage
savePreference("fade"); // Stores preference
console.log(getPreference()); // Retrieves stored preference

document.addEventListener("DOMContentLoaded", function () {
    const button = document.getElementById("animateButton");
    
    button.addEventListener("click", function () {
        let animationType = getPreference();
        button.style.animation = `${animationType} 0.5s ease-in-out`;

        // Remove animation after it completes
        setTimeout(() => {
            button.style.animation = "";
        }, 500);
    });
});

--HTML--
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Animation & LocalStorage</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <button id="animateButton" class="animated-button">Click Me</button>

    <script src="script.js"></script>
</body>
</html>
