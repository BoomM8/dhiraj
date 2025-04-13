


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Student Info + Teacher Profile</title>
  <style>
    body, html {
      height: 100%;
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: url('https://gonintendo.com/uploads/file_upload/upload/71539/prairie.png') no-repeat center center fixed;
      background-size: cover;
    }

    .container {
      display: flex;
      justify-content: center;
      align-items: flex-start;
      gap: 50px;
      padding: 50px;
      flex-wrap: wrap;
    }

    .form-container, .instruction {
      background: rgba(255, 255, 255, 0.95);
      border-radius: 20px;
      box-shadow: 0 8px 16px rgba(0,0,0,0.2);
      padding: 30px;
      width: 350px;
    }

    .instruction {
      font-size: 16px;
      color: #333;
      background: #fff8f0;
    }

    h2 {
      text-align: center;
      margin-bottom: 20px;
      color: #e91e63;
    }

    input, textarea, select, button {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      font-size: 16px;
      border-radius: 8px;
      border: 1px solid #ccc;
    }

    button {
      background-color: #ff6f61;
      color: white;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s ease;
    }

    button:hover {
      background-color: #e54e4e;
    }

    .confirmation {
      display: none;
      margin-top: 10px;
      font-size: 16px;
      text-align: center;
      color: green;
      animation: fadeIn 0.8s ease-in-out;
    }

    @keyframes fadeIn {
      0% { opacity: 0; transform: translateY(-10px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    .teacher-card {
      background: rgba(255,255,255,0.95);
      border-radius: 20px;
      box-shadow: 0 8px 16px rgba(0,0,0,0.2);
      padding: 30px;
      margin: 20px auto;
      width: 350px;
    }

    .teacher-card img {
      width: 120px;
      height: 120px;
      border-radius: 50%;
      object-fit: cover;
      margin: 0 auto;
      display: block;
      border: 3px solid #ff6f61;
    }

    .teacher-card h3 {
      text-align: center;
      margin-top: 15px;
      font-size: 22px;
      color: #333;
    }

    .teacher-card p {
      margin: 8px 0;
      font-size: 15px;
      line-height: 1.5;
    }

    @media screen and (max-width: 800px) {
      .container {
        flex-direction: column;
        align-items: center;
      }
    }
  </style>
</head>
<body>

<div class="container">
  <!-- Student Info Form -->
  <div class="form-container">
    <h2>Student Information</h2>
    <form id="studentForm">
      <input type="text" id="name" placeholder="Name" required>
      <input type="text" id="father" placeholder="Father's Name" required>
      <input type="text" id="mother" placeholder="Mother's Name" required>
      <textarea id="address" placeholder="Enter your address" required></textarea>
      <input type="text" id="class" placeholder="Class" required>
      <select id="board" required>
        <option value="">Select Board</option>
        <option value="ICSE">ICSE</option>
        <option value="CBSE">CBSE</option>
        <option value="State">State</option>
      </select>
      <input type="text" id="mathsMarks" placeholder="Last Year's 3rd Term Maths Marks" required>
      <input type="text" id="phone" placeholder="Phone Number" required>
      <button type="submit">Submit</button>
      <div class="confirmation" id="confirmationMessage">✅ Information prepared! Click 'Send' on WhatsApp to complete submission.</div>
    </form>
  </div>

  <!-- Instructions -->
  <div class="instruction">
    <h2>Instructions</h2>
    <p>👉 Fill out the form with correct information.</p>
    <p>👉 Click the <strong>Submit</strong> button.</p>
    <p>👉 A WhatsApp message will open with your details filled in.</p>
    <p>👉 Simply click <strong>Send</strong> on WhatsApp to complete the process.</p>
  </div>
</div>

<!-- Teacher Card Below -->
<div class="teacher-card">
  <h3>Mr. Nagaraju.YS</h3>
  <p><strong>🎓 Graduated from:</strong> Bangalore University</p>
  <p><strong>📘 Expertise:</strong> Mathematics, Logical Reasoning, IIT Foundation</p>
  <p><strong>🕒 Experience:</strong> 25+ years</p>
  <p><strong>🏆 Achievements:</strong> Best Maths Teacher Award</p>
  <p><strong>📍 Location:</strong> <a href="https://g.co/kgs/Hck9NZw" target="_blank">Bengaluru, Karnataka</a></p>
</div>

<script>
  document.getElementById("studentForm").addEventListener("submit", function(e) {
    e.preventDefault();

    const name = document.getElementById("name").value;
    const father = document.getElementById("father").value;
    const mother = document.getElementById("mother").value;
    const address = document.getElementById("address").value;
    const studentClass = document.getElementById("class").value;
    const board = document.getElementById("board").value;
    const mathsMarks = document.getElementById("mathsMarks").value;
    const phone = document.getElementById("phone").value;

    const message = `Name: ${name}%0AFather's Name: ${father}%0AMother's Name: ${mother}%0AAddress: ${address}%0AClass: ${studentClass}%0ABoard: ${board}%0AMaths 3rd Term Marks: ${mathsMarks}%0APhone: ${phone}`;
    const teacherNumber = "9448268530";
    const whatsappURL = `https://api.whatsapp.com/send?phone=${teacherNumber}&text=${message}`;

    const confirmation = document.getElementById("confirmationMessage");
    confirmation.style.display = "block";

    setTimeout(() => {
      window.open(whatsappURL, "_blank");
    }, 1000);
  });
</script>

</body>
</html>
