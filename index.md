---
layout: default
title: What The Cats
---

<div class="hero-section">
    <div class="hero-content">
        <h1 class="animate-fade-in">Welcome to What The Cats</h1>
        <p class="server-ip animate-slide-up">Server IP: <span class="copyable" onclick="copyToClipboard('{{ site.server_ip }}')">{{ site.server_ip }}</span></p>
        <div class="server-status">
            <div class="status-indicator"></div>
            <span class="player-count">Loading players...</span>
        </div>
        <div class="cta-buttons animate-fade-in">
            <a href="{{ site.discord_invite }}" class="btn btn-primary pulse-effect">
                <i class="fab fa-discord"></i> Join Discord
            </a>
            <a href="{{ site.store_url }}" class="btn btn-secondary glow-effect">
                <i class="fas fa-store"></i> Visit Store
            </a>
        </div>
    </div>
    <div class="hero-background"></div>
</div>

<div class="features-section">
    <div class="feature-grid">
        <div class="feature animate-on-scroll">
            <div class="feature-icon">
                <i class="fas fa-gamepad"></i>
            </div>
            <h2>Unique Gameplay</h2>
            <p>Experience Minecraft like never before with our custom features and plugins!</p>
        </div>
        <div class="feature animate-on-scroll">
            <div class="feature-icon">
                <i class="fas fa-users"></i>
            </div>
            <h2>Amazing Community</h2>
            <p>Join our friendly community of players from around the world!</p>
        </div>
        <div class="feature animate-on-scroll">
            <div class="feature-icon">
                <i class="fas fa-shield-alt"></i>
            </div>
            <h2>Fair Play</h2>
            <p>We ensure a balanced and safe environment for all players.</p>
        </div>
        <div class="feature animate-on-scroll">
            <div class="feature-icon">
                <i class="fas fa-server"></i>
            </div>
            <h2>High Performance</h2>
            <p>Enjoy lag-free gameplay with our powerful dedicated servers!</p>
        </div>
    </div>
</div>

<div class="news-section parallax-bg">
    <h2 class="section-title">Latest Updates</h2>
    <div class="announcements-grid">
        {% for announcement in site.announcements limit:3 %}
        <div class="announcement-card animate-on-scroll">
            <div class="announcement-header">
                <span class="announcement-date">{{ announcement.date | date: "%B %d, %Y" }}</span>
                <h3>{{ announcement.title }}</h3>
            </div>
            <div class="announcement-content">
                {{ announcement.excerpt }}
            </div>
            <a href="{{ announcement.url }}" class="read-more-link">
                Read More <i class="fas fa-arrow-right"></i>
            </a>
        </div>
        {% endfor %}
    </div>
</div>

<div class="social-section">
    <h2 class="section-title">Connect With Us</h2>
    <div class="social-links">
        <a href="https://discord.gg/{{ site.social.discord }}" class="social-link discord">
            <i class="fab fa-discord"></i>
            <span>Discord</span>
        </a>
        <a href="https://twitter.com/{{ site.social.twitter }}" class="social-link twitter">
            <i class="fab fa-twitter"></i>
            <span>Twitter</span>
        </a>
        <a href="https://youtube.com/{{ site.social.youtube }}" class="social-link youtube">
            <i class="fab fa-youtube"></i>
            <span>YouTube</span>
        </a>
    </div>
</div>
