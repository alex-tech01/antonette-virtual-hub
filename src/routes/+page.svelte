<script>
    import { fade } from "svelte/transition";

    let name = "";
    let email = "";
    let message = "";
    let formSubmitted = false;
    let error = "";

    function handleSubmit() {
        if (!name || !email || !message) {
            error = "Please fill out all fields.";
            formSubmitted = false;
        } else {
            error = "";
            formSubmitted = true;
            console.log("Form Submitted:", { name, email, message });
            name = "";
            email = "";
            message = "";
        }
    }
</script>

<header>
    <h1>Antonette Virtual Hub</h1>
    <p>Your trusted partner in professional virtual assistant services.</p>
    <nav>
        <a href="/">Home</a>
        <a href="/portfolio">Portfolio</a>
        <a href="#about">About</a>
        <a href="#services">Services</a>
        <a href="#contact">Contact</a>
    </nav>
</header>

<section id="about" in:fade>
    <h2>About Me</h2>
    <p>
        Hello! I'm Antonette, a dedicated Virtual Assistant passionate about
        helping businesses and individuals streamline their operations, maximize
        their productivity, and achieve their goals. I bring professionalism,
        flexibility, and confidentiality to every task. Let's work together to
        make your success inevitable!
    </p>
</section>

<section id="services" in:fade>
    <h2>Services Offered</h2>
    <ul>
        <li>💻 Software Development</li>
        <li>📧 Email Management & Inbox Organization</li>
        <li>📅 Calendar Management & Scheduling</li>
        <li>📞 Client Communication (Email, Chat, Phone)</li>
        <li>📱 Social Media Management & Content Scheduling</li>
        <li>📨 Email Marketing Campaigns</li>
        <li>🗂️ Project Management & Task Tracking</li>
        <li>📊 Report & Presentation Preparation</li>
        <li>🗄️ File Management & Organization</li>
        <li>🌐 Internet Research & Data Gathering</li>
        <li>🛫 Travel Planning & Itinerary Creation</li>
        <li>⌨️ Data Entry & Basic Data Analysis</li>
        <li>🧩 CRM Management (e.g., HubSpot, Zoho, Salesforce)</li>
        <li>🖥️ Google Workspace & Microsoft Office Suite</li>
        <li>🛠️ Administrative Support</li>
        <li>⏳ Time Management & Prioritization</li>
        <li>🧠 Problem Solving & Decision Making</li>
        <li>🔍 High Attention to Detail</li>
        <li>🔒 Confidentiality & Professionalism</li>
        <li>🔄 Flexible & Adaptable to Client Needs</li>
    </ul>
</section>

<section id="contact" in:fade>
    <h2>Ready to Work Together?</h2>
    <p>Fill out the form below and let's connect!</p>

    <form
        action="https://formspree.io/f/mnndjodd"
        method="POST"
        on:submit={() => (formSubmitted = true)}
    >
        <input type="text" name="name" placeholder="Your Name" required />
        <input type="email" name="email" placeholder="Your Email" required />
        <textarea name="message" placeholder="Your Message" rows="5" required
        ></textarea>
        <button type="submit">Send Message</button>

        {#if formSubmitted}
            <div class="success">Thank you! Your message has been sent.</div>
        {/if}
    </form>
</section>

<footer>© 2025 Antonette Virtual Hub</footer>

<style>
    header {
        background: url("https://images.unsplash.com/photo-1504384308090-c894fdcc538d?ixlib=rb-4.0.3&auto=format&fit=crop&w=1950&q=80")
            no-repeat center center/cover;
        color: white;
        padding: 6rem 1rem 4rem;
        text-align: center;
        position: relative;
    }

    header::after {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background-color: rgba(0, 0, 0, 0.5);
    }

    header h1 {
        margin: 0;
        font-size: 3rem;
        position: relative;
        z-index: 1;
    }

    header p {
        margin-top: 1rem;
        font-size: 1.2rem;
        position: relative;
        z-index: 1;
    }

    nav {
        margin-top: 2rem;
        position: relative;
        z-index: 1;
    }

    nav a,
    button {
        background: #ffffffcc;
        color: #4a90e2;
        padding: 0.8rem 1.5rem;
        margin: 0.5rem;
        text-decoration: none;
        border-radius: 30px;
        font-weight: bold;
        display: inline-block;
        transition: all 0.3s ease;
        border: 2px solid #4a90e2;
    }

    nav a:hover,
    button:hover {
        background: #4a90e2;
        color: white;
    }

    section {
        padding: 3rem 2rem;
        max-width: 1000px;
        margin: 0 auto;
    }

    h2 {
        color: #333;
        margin-bottom: 1rem;
    }

    ul {
        list-style: none;
        padding: 0;
        columns: 2;
        column-gap: 2rem;
    }

    ul li {
        margin-bottom: 0.8rem;
        font-size: 1.1rem;
    }

    form {
        display: flex;
        flex-direction: column;
        gap: 1rem;
        margin-top: 2rem;
    }

    input,
    textarea {
        padding: 0.8rem;
        font-size: 1rem;
        border: 1px solid #ccc;
        border-radius: 6px;
        width: 100%;
    }

    button {
        cursor: pointer;
    }

    .success {
        color: green;
        margin-top: 1rem;
    }

    .error {
        color: red;
        margin-top: 1rem;
    }

    footer {
        text-align: center;
        padding: 2rem 1rem;
        font-size: 0.9rem;
        color: #777;
    }

    @media (max-width: 768px) {
        ul {
            columns: 1;
        }
    }
</style>
