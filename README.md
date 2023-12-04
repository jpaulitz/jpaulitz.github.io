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
            display: flex;
            flex-direction: column;
            align-items: center;
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
            margin: 5px;
            cursor: pointer;
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

        <!-- D3.js Bubble Chart Visualization -->
        <section class="section">
            <h2>Work History Visualization</h2>
            <div class="bubble-chart-container" id="bubble-chart-container"></div>
        </section>
    </div>

    <!-- D3.js Code for Bubble Chart -->
    <script src="https://d3js.org/d3.v7.min.js"></script>
    <script>
        // Sample data for the bubble chart
        var data = [
            { jobTitle: "Job 1", company: "Company A", startDate: "2020-01-01", endDate: "2022-06-30" },
            { jobTitle: "Job 2", company: "Company B", startDate: "2019-04-15", endDate: "2020-01-15" },
            { jobTitle: "Job 3", company: "Company C", startDate: "2017-08-10", endDate: "2019-03-20" }
        ];

        // Create a function to calculate the duration of each job in months
        function calculateDuration(startDate, endDate) {
            var start = new Date(startDate);
            var end = new Date(endDate);
            var months = (end.getFullYear() - start.getFullYear()) * 12;
            months -= start.getMonth();
            months += end.getMonth();
            return months <= 0 ? 0 : months;
        }

        // Set up the SVG canvas for the bubble chart
        var svg = d3.select("#bubble-chart-container")
            .append("svg")
            .attr("width", 400)
            .attr("height", 200);

        // Create bubbles for each job
        var bubbles = svg.selectAll("circle")
            .data(data)
            .enter()
            .append("circle")
            .attr("cx", function (d, i) { return i * 100 + 50; })
            .attr("cy", 100)
            .attr("r", function (d) { return Math.sqrt(calculateDuration(d.startDate, d.endDate)) * 10; })
            .style("fill", "#007bff")
            .style("opacity", 0.7)
            .style("cursor", "pointer");

        // Add labels inside the bubbles
        svg.selectAll(null)
            .data(data)
            .enter()
            .append("text")
            .text(function (d) { return d.jobTitle; })
            .attr("x", function (d, i) { return i * 100 + 50; })
            .attr("y", 100)
            .style("fill", "#fff")
            .style("text-anchor", "middle")
            .style("alignment-baseline", "middle")
            .style("font-size", "12px");

        // Add click event to the bubbles
        bubbles.on("click", function (d) {
            alert("Job: " + d.jobTitle + "\nCompany: " + d.company);
        });
    </script>
</body>
</html>
