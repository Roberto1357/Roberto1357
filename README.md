- 👋 Hi, I’m @Roberto1357
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Roberto1357/Roberto1357 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Egg Opener Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f7f7f7;
            padding: 20px;
        }
        .button {
            padding: 15px 25px;
            font-size: 20px;
            color: #fff;
            background-color: #007BFF;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .button:hover {
            background-color: #0056b3;
        }
        .output {
            margin-top: 20px;
            font-size: 18px;
            color: #333;
        }
    </style>
</head>
<body>
    <h1>Egg Opener Simulator</h1>
    <button class="button" onclick="openEgg()">Open Egg</button>
    <div class="output" id="output">Click the button to open an egg!</div>

    <script>
        // Pets and their probabilities
        const pets = [
            { name: "Common Cat", chance: 60.0 },
            { name: "Common Dog", chance: 20.0 },
            { name: "Uncommon Bird", chance: 10.0 },
            { name: "Rare Fox", chance: 5.0 },
            { name: "Epic Dragon", chance: 2.5 },
            { name: "Legendary Unicorn", chance: 1.0 },
            { name: "Mythic Phoenix", chance: 0.5 },
            { name: "Divine Tiger", chance: 0.25 },
            { name: "Godly Wolf", chance: 0.1 },
            { name: "Celestial Whale", chance: 0.05 },
            { name: "Stellar Griffin", chance: 0.02 },
            { name: "Galactic Serpent", chance: 0.01 },
            { name: "Astral Beast", chance: 0.005 },
            { name: "Ethereal Spirit", chance: 0.001 },
            { name: "Ultimate Egglord", chance: 0.00001 },
        ];

        // Calculate total chance
        const totalChance = pets.reduce((sum, pet) => sum + pet.chance, 0);

        // Function to draw a random pet
        function openEgg() {
            const random = Math.random() * totalChance;
            let cumulativeChance = 0;

            for (const pet of pets) {
                cumulativeChance += pet.chance;
                if (random <= cumulativeChance) {
                    document.getElementById("output").innerText = `You got: ${pet.name}`;
                    return;
                }
            }

            document.getElementById("output").innerText = "No pet found (this shouldn't happen!)";
        }
    </script>
</body>
</html>
