<script>
    import { fade } from "svelte/transition";

    const portfolioItems = [
        {
            title: "Client Email Marketing Revamp",
            description:
                "Created and scheduled a 3-month email campaign using Mailchimp. Open rate increased by 35%.",
            tools: ["Mailchimp", "Canva", "Copywriting"],
        },
        {
            title: "Project Management Setup",
            description:
                "Organized tasks, deadlines, and workflows for a startup team using Trello and Notion.",
            tools: ["Trello", "Notion", "Slack"],
        },
        {
            title: "Custom CRM Data Entry",
            description:
                "Imported and cleaned 1,200+ customer records into HubSpot with tagging and segmentation.",
            tools: ["HubSpot", "Excel", "Zapier"],
        },
        {
            title: "Website Maintenance Support",
            description:
                "Provided ongoing virtual support for a coaching business: website edits, calendar updates, and contact form handling.",
            tools: ["Squarespace", "Google Calendar", "Gmail"],
        },
    ];
</script>

<section in:fade>
    <h1>My Portfolio</h1>
    <div class="grid">
        {#each portfolioItems as item (item.title)}
            <div class="card">
                <h2>{item.title}</h2>
                <p>{item.description}</p>
                <div class="tools">Tools used: {item.tools.join(", ")}</div>
            </div>
        {/each}
    </div>

    <a href="/" class="back-link">← Back to Home</a>
</section>

<style>
    section {
        padding: 3rem 2rem;
        max-width: 1000px;
        margin: 0 auto;
    }

    h1 {
        text-align: center;
        color: #4a90e2;
        margin-bottom: 2rem;
    }

    .grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
        gap: 2rem;
    }

    .card {
        background: white;
        border: 1px solid #eee;
        border-radius: 10px;
        padding: 1.5rem;
        box-shadow: 0 0 8px rgba(0, 0, 0, 0.05);
        transition: transform 0.2s ease;
    }

    .card:hover {
        transform: scale(1.03);
    }

    .card h2 {
        font-size: 1.2rem;
        color: #333;
        margin-bottom: 0.5rem;
    }

    .card p {
        font-size: 0.95rem;
        margin-bottom: 0.8rem;
    }

    .tools {
        font-size: 0.85rem;
        color: #777;
    }

    .back-link {
        display: block;
        text-align: center;
        margin-top: 3rem;
        font-weight: bold;
        color: #4a90e2;
        text-decoration: none;
    }

    .back-link:hover {
        text-decoration: underline;
    }
</style>
