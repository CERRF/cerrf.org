---
title: "Project Repositories"
layout: default
---

# Project Repositories

Browse our GitHub repositories below:

<div class="repo-container">
    <div class="repo-card" id="repo1">
        <h3>GitHub Repository 1</h3>
        <p>Description of the first repository.</p>
        <a href="https://github.com/cerrf-org/repo1" target="_blank">View on GitHub</a>
    </div>
    <div class="repo-card" id="repo2">
        <h3>GitHub Repository 2</h3>
        <p>Description of the second repository.</p>
        <a href="https://github.com/cerrf-org/repo2" target="_blank">View on GitHub</a>
    </div>
    <div class="repo-card" id="repo3">
        <h3>GitHub Repository 3</h3>
        <p>Description of the third repository.</p>
        <a href="https://github.com/cerrf-org/repo3" target="_blank">View on GitHub</a>
    </div>
</div>

<style>
    .repo-container {
        display: flex;
        flex-wrap: wrap;
        gap: 20px;
        justify-content: center;
        padding: 20px;
    }
    .repo-card {
        background: #24292e;
        color: #fff;
        padding: 20px;
        border-radius: 8px;
        box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        width: 300px;
        text-align: center;
    }
    .repo-card h3 {
        color: #f6f8fa;
    }
    .repo-card a {
        color: #58a6ff;
        text-decoration: none;
        font-weight: bold;
    }
    .repo-card a:hover {
        text-decoration: underline;
    }
</style>

<script>
    async function fetchGitHubRepos() {
        const repos = ["repo1", "repo2", "repo3"];
        const org = "cerrf-org";
        
        repos.forEach(async repo => {
            const response = await fetch(`https://api.github.com/repos/${org}/${repo}`);
            const data = await response.json();
            
            document.getElementById(repo).innerHTML = `
                <h3>${data.name}</h3>
                <p>${data.description || "No description available."}</p>
                <a href="${data.html_url}" target="_blank">View on GitHub</a>
            `;
        });
    }
    fetchGitHubRepos();
</script>
