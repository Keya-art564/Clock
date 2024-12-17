<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Transparent Spider-Man Clock</title>
  <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&display=swap" rel="stylesheet">
  <style>
    /* General Body Styling */
    body {
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      color: #fff;
      font-family: 'Bebas Neue', sans-serif;
      background: url('https://i.pinimg.com/originals/f6/0a/63/f60a6366de874b4e9e7f61681f5b7ce6.gif') no-repeat center center/cover;
      overflow: hidden;
    }

    /* Overlay for better text visibility */
    .overlay {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.3); /* Slight dark overlay */
      z-index: 1;
    }

    /* Clock Container - Transparent */
    .clock {
      position: relative;
      z-index: 2;
      padding: 2rem 4rem;
      text-align: center;
      border: 3px solid rgba(255, 0, 0, 0.8); /* Semi-transparent border */
      border-radius: 15px;
      backdrop-filter: blur(10px); /* Blur effect */
      background: rgba(0, 0, 0, 0.3); /* Transparent black background */
      box-shadow: 0 0 20px rgba(255, 0, 0, 0.7), 0 0 40px rgba(255, 0, 0, 0.5);
    }

    /* Time Styling - Changed to White */
    #time {
      font-size: 4.5rem;
      font-weight: bold;
      color: #ffffff; /* White */
      text-shadow: 0 0 10px #ffffff, 0 0 20px #ffffff, 0 0 30px #ffffff;
      letter-spacing: 5px;
    }

    /* Day Styling */
    #day {
      font-size: 2rem;
      margin-top: 1rem;
      color: #f39c12; /* Gold */
      text-shadow: 0 0 10px #f39c12, 0 0 20px #f39c12;
    }

    /* Date Styling */
    #date {
      font-size: 1.5rem;
      margin-top: 0.5rem;
      color: #3498db; /* Blue */
      text-shadow: 0 0 10px #3498db, 0 0 20px #3498db;
    }

    /* Footer - Without Spider Emoji */
    .footer {
      margin-top: 1.5rem;
      font-size: 1rem;
      color: #fff;
      text-shadow: 0 0 5px #fff;
      opacity: 0.8;
      text-transform: uppercase;
      letter-spacing: 2px;
    }
  </style>
</head>
<body>
  <!-- Overlay -->
  <div class="overlay"></div>

  <!-- Clock Container -->
  <div class="clock">
    <div id="time">00:00:00</div>
    <div id="day">Monday</div>
    <div id="date">June 5, 2024</div>
    <div class="footer">Your Friendly Neighborhood Clock</div> <!-- Removed the Spider emoji -->
  </div>

  <script>
    // Function to update the time, day, and date
    function updateClock() {
      const now = new Date();

      // Fetch hours, minutes, seconds
      let hours = now.getHours().toString().padStart(2, '0');
      let minutes = now.getMinutes().toString().padStart(2, '0');
      let seconds = now.getSeconds().toString().padStart(2, '0');

      // Fetch day of the week
      const days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
      let day = days[now.getDay()];

      // Fetch date in "Month Day, Year" format
      const months = [
        "January", "February", "March", "April", "May", "June",
        "July", "August", "September", "October", "November", "December"
      ];
      let month = months[now.getMonth()];
      let date = now.getDate();
      let year = now.getFullYear();

      // Update HTML content
      document.getElementById('time').innerText = `${hours}:${minutes}:${seconds}`;
      document.getElementById('day').innerText = day;
      document.getElementById('date').innerText = `${month} ${date}, ${year}`;
    }

    // Update clock every second
    setInterval(updateClock, 1000);
    updateClock(); // Run once on load
  </script>
</body>
</html>
