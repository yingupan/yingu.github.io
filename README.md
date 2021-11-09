<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="utf-8">
		<title>PSET7 D3 Visualization Webpage</title>
		<script src="https://cdnjs.cloudflare.com/ajax/libs/d3/7.1.1/d3.min.js"></script>
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet">
		<link href="https://fonts.googleapis.com/css?family=Open+Sans:300,500" rel="stylesheet">
		<style type="text/css">

		</style>
		</head>
		<body>
            <main role="main" class="container" >
                <div class="row">
                    
                    <br><br>
                    <h1>Visualizing Agricultural Land</h1>
                    <hr>
                
                </div>

                <div class="row">
                    <div class="col-5">

                        <br><br>
                        <h7>Lorem Ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.Ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.<h7>
                        <br><br>
                        <h5>Big Data, Visualization, and Society<h5>
                        <h6>Course： 11.154/11.454 <h6>
                        <h6>Assignment: PSET7-D3 Visualization Webpage <h6>
                        <h6>Author: Yingu Pan <h6>

  
                    </div>

                    <div class="col-7">

                        <br><br>
                        <div id="viz"></div>
                        <hr>
                    </div>

                </div>


        <main>
            <div id="viz"></div>

        </main>
		<script type="text/javascript">
            const agriculturedata = [
                ["Brazil", 33.9],
                ["Canada", 6.9],
                ["Costa Rica", 34.5],
                ["Denmark", 62],
                ["Fiji", 23.3],
                ["France", 52.4],
                ["Greenland", .6],
                ["Italy", 43.2],
                ["Mali",33.8],
                ["Netherlands",53.3]
            ];

			const width = 1200;
			const height = 1000;
            const marginLeft = 100;
            const marginTop = 50;
            const barHeight = 30;
            const widthMultiplier = 6;
            const gap = 5;

            // define svg
			const svg = d3.select("#viz")
                .append("svg")
                .attr("width", width)
                .attr("height", height);
			
            // add rectangle bars
            svg.append("g")
                .attr("class", "rect-bars")
            .selectAll("rect")
                .data(agriculturedata)
                .enter()
                .append("rect")
                    .attr("y", (d, i) => i * (barHeight + gap) + marginTop)
                    .attr("x",  marginLeft)
                    .attr("width", d => d[1] * widthMultiplier)
                    .attr("height", barHeight)
                    .attr("fill", "green")
                    .style("opacity", 0.7)

            svg.append("g")
                    .attr("class", "labels")
                .selectAll("text")
                .data(agriculturedata)
                .enter()
                .append("text")
                    .attr("y", (d, i) => i * (barHeight + gap) + marginTop+8)
                    .attr("x", 95)
                    .attr("dy", "1em")
                    .attr("text-anchor", "end")
                    .attr("font-size", "14px")
                    .attr("fill", "black")
                    .text(d => d[0])

            svg.append("g")
                    .attr("class", "labels")
                .selectAll("text")
                .data(agriculturedata)
                .enter()
                .append("text")
                    .attr("y", (d, i) => i * (barHeight + gap) + marginTop+8)
                    .attr("x", d => d[1]* widthMultiplier+140)
                    .attr("dy", "1em")
                    .attr("text-anchor", "end")
                    .attr("font-size", "14px")
                    .attr("fill", "black")
                    .text(d => d[1]+"%")

            svg.append("g")
                    .attr("class", "title-styling")
                .append("text")
                    .attr("y",20)
                    .attr("x",100)
                    .attr("dy", "1em")
                    .attr("text-anchor", "left")
                    .attr("font-size", "18px")
                    .attr("fill", "black")
                    .text("Proportion of Agricultural Land in 2016")
                    ;
		</script>
        
	</body>
</html>
© 2021 GitHub, Inc.
Terms
Privacy
Security
Status
Docs
Contact GitHub
Pricing
API
Training
Blog
About
