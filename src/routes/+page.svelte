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
        <a href="#about">About Me</a>
        <a href="#services">Services</a>
        <a href="#contact">Contact</a>
    </nav>
</header>

<section id="about">
    <h2>About Me</h2>
    <p>
        Hello! I'm Antonette, a dedicated Virtual Assistant passionate about
        helping businesses and individuals streamline their operations, maximize
        their productivity, and achieve their goals. I bring professionalism,
        flexibility, and confidentiality to every task. Let's work together to
        make your success inevitable!
    </p>
</section>

<section id="services">
    <h2>Services Offered</h2>
    <ul>
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

<section id="contact">
    <h2>Ready to Work Together?</h2>
    <p>Fill out the form below and let's connect!</p>

    <form on:submit|preventDefault={handleSubmit}>
        <input type="text" placeholder="Your Name" bind:value={name} />
        <input type="email" placeholder="Your Email" bind:value={email} />
        <textarea placeholder="Your Message" rows="5" bind:value={message}
        ></textarea>
        <button type="submit">Send Message</button>

        {#if error}
            <div class="error">{error}</div>
        {/if}

        {#if formSubmitted && !error}
            <div class="success">Thank you! Your message has been sent.</div>
        {/if}
    </form>
</section>

<footer>© 2025 Antonette Virtual Hub</footer>

<style>
    /* Same styles from before, plus a little extra for the form */
    body {
        font-family: Arial, sans-serif;
        margin: 0;
        padding: 0;
        background: #f9f9f9;
    }

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
        background-color: rgba(0, 0, 0, 0.5); /* Dark transparent overlay */
    }

    nav {
        margin-top: 2rem;
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
        background-color: #4a90e2;
        color: white;
        padding: 0.8rem 1.5rem;
        border: none;
        border-radius: 6px;
        font-size: 1rem;
        cursor: pointer;
    }

    button:hover {
        background-color: #357abd;
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
