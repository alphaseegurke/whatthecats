---
layout: default
title: What The Cats
---

<div class="hero-section">
    <h1>Welcome to What The Cats</h1>
    <p class="server-ip">Server IP: {{ site.server_ip }}</p>
    <div class="cta-buttons">
        <a href="{{ site.discord_invite }}" class="btn btn-primary">Join our Discord</a>
        <a href="{{ site.store_url }}" class="btn btn-secondary">Visit Store</a>
    </div>
</div>

<div class="features-section">
    <div class="feature">
        <h2>🎮 Unique Gameplay</h2>
        <p>Experience Minecraft like never before with our custom features and plugins!</p>
    </div>
    <div class="feature">
        <h2>🌟 Amazing Community</h2>
        <p>Join our friendly community of players from around the world!</p>
    </div>
    <div class="feature">
        <h2>🛡️ Fair Play</h2>
        <p>We ensure a balanced and safe environment for all players.</p>
    </div>
</div>

<div class="news-section">
    <h2>Latest News</h2>
    <div class="announcements">
        {% for announcement in site.announcements limit:3 %}
        <div class="announcement">
            <h3>{{ announcement.title }}</h3>
            <p class="date">{{ announcement.date | date: "%B %d, %Y" }}</p>
            {{ announcement.excerpt }}
            <a href="{{ announcement.url }}" class="read-more">Read More</a>
        </div>
        {% endfor %}
    </div>
</div>

<div class="social-section">
    <h2>Connect With Us</h2>
    <div class="social-links">
        <a href="https://discord.gg/{{ site.social.discord }}" class="social-link discord">Discord</a>
        <a href="https://twitter.com/{{ site.social.twitter }}" class="social-link twitter">Twitter</a>
        <a href="https://youtube.com/{{ site.social.youtube }}" class="social-link youtube">YouTube</a>
    </div>
</div>
