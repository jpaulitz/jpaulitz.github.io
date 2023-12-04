<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Bubble CV</title>
    <style>
        /* Add your CSS styles here */
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
            margin: 0;
            padding: 0;
        }

        header {
            background-color: #333;
            color: #fff;
            text-align: center;
            padding: 20px 0;
        }

        h1 {
            font-size: 36px;
            margin: 0;
        }

        .container {
            max-width: 800px;
            margin: 20px auto;
            padding: 20px;
            background-color: #fff;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            border-radius: 5px;
        }

        .section {
            margin-bottom: 20px;
        }

        h2 {
            font-size: 24px;
            margin-bottom: 10px;
        }

        p {
            font-size: 16px;
        }

        .skills {
            display: flex;
            flex-wrap: wrap;
        }

        .skill {
            background-color: #333;
            color: #fff;
            padding: 5px 10px;
            border-radius: 5px;
            margin: 5px;
        }

        /* Visual representation of the CV */
        .bubble-chart-container {
            position: relative;
            width: 100%;
            height: 200px;
            background-color: #f5f5f5;
        }

        .bubble {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background-color: #007bff;
            color: #fff;
            text-align: center;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            position: absolute;
        }

        .timeline {
            position: absolute;
            top: 50%;
            left: 0;
            width: 100%;
            height: 4px;
            background-color: #ccc;
        }

        /* Add more CSS styles for visual elements and animations */
    </style>
</head>
<body>
    <header>
        <h1>Your Name</h1>
        <p>Bubble CV</p>
    </header>

    <div class="container">
        <section class="section">
            <h2>About Me</h2>
            <p>
                Write a brief introduction about yourself here. Highlight your skills, passions, and what makes you unique.
            </p>
        </section>

        <section class="section">
            <h2>Education</h2>
            <p>
                <strong>University Name</strong><br>
                Bachelor of Science in Computer Science<br>
                Graduation Year: 20XX
            </p>
        </section>

        <section class="section">
            <h2>Work Experience</h2>
            <p>
                <strong>Job Title</strong><br>
                Company Name<br>
                Dates: Month Year - Month Year<br>
                Description of your responsibilities and achievements.
            </p>
        </section>

        <section class="section">
            <h2>Skills</h2>
            <div class="skills">
                <div class="skill">HTML</div>
                <div class="skill">CSS</div>
                <div class="skill">JavaScript</div>
                <div class="skill">Graphic Design</div>
                <div class="skill">Teamwork</div>
                <div class="skill">Problem Solving</div>
            </div>
        </section>

        <!-- Bubble Chart Section -->
        <section class="section">
            <h2>Work History Visualization</h2>
            <div class="bubble-chart-container">
                <!-- Timeline -->
                <div class="timeline"></div>
                <!-- Bubbles for Jobs -->
                <div class="bubble" style="left: 10%; bottom: 50px;">Job 1</div>
                <div class="bubble" style="left: 40%; bottom: 50px;">Job 2</div>
                <div class="bubble" style="left: 70%; bottom: 50px;">Job 3</div>
                <!-- Last Bubble -->
                <div class="bubble last-bubble" style="left: 95%; bottom: 50px;">
                    This could be your company
                </div>
            </div>
        </section>
    </div>
</body>
</html>
