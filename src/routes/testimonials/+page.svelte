<script>
    import { fade } from "svelte/transition";

    const testimonials = [
        {
            name: "L. Tucker, Coaching Consultant",
            text: "Working with Antonette has streamlined my entire schedule. She is proactive, organized, and always one step ahead. Highly recommended!",
        },
        {
            name: "James M., Tech Startup Founder",
            text: "Antonette helped bring order to our chaos — from calendar management to CRM setup. Truly a life-saver!",
        },
        {
            name: "Maria G., E-commerce Owner",
            text: "Responsive, friendly, and detail-oriented. My inbox has never been this peaceful!",
        },
        {
            name: "Angie Newton - HerGrandLife.com & GetASocialBoost.com",
            text: "Antonette has been such a blessing to work with! She rewrites PLR content for my blog, creates guides, handles research, does spreadsheets, and even puts together YouTube videos from photos.\n\nGreat communication, especially with us being in different parts of the world. She’s always responsive and reliable. And she’s dependable, proactive, and talented too.\n\nWhat I appreciate most is how she seems to know what I need before I even ask. She takes on new tasks without hesitation. She’s quick to learn new things and always makes my workload lighter and my business run smoother.\n\nHiring Antonette was a total game-changer! I highly recommend working with her! She’s truly an asset to my team!",
        },
    ];
</script>

<section in:fade>
    <h1>What My Clients Say</h1>
    {#each testimonials as t (t.name)}
        <div class="testimonial">
            <p>"{t.text}"</p>
            <div class="name">— {t.name}</div>
        </div>
    {/each}

    <a href="/" class="back-link">← Back to Home</a>
</section>

<style>
    section {
        padding: 3rem 2rem;
        max-width: 900px;
        margin: 0 auto;
        text-align: center;
    }

    h1 {
        color: #4a90e2;
        margin-bottom: 2.5rem;
    }

    .testimonial {
        background: #ffffff;
        border-radius: 12px;
        padding: 2rem;
        margin-bottom: 2rem;
        box-shadow: 0 4px 14px rgba(0, 0, 0, 0.05);
        transition: transform 0.3s ease;
    }

    .testimonial:hover {
        transform: scale(1.02);
    }

    .testimonial p {
        font-size: 1.1rem;
        font-style: italic;
        color: #333;
        margin-bottom: 1.2rem;
    }

    .testimonial .name {
        font-weight: bold;
        color: #4a90e2;
    }

    .back-link {
        display: inline-block;
        margin-top: 3rem;
        font-weight: bold;
        color: #4a90e2;
        text-decoration: none;
    }

    .back-link:hover {
        text-decoration: underline;
    }
</style>
