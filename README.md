index.html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="UNICAL News Update — campus, education and Nigerian headlines.">
  <title>UNICAL News Update | Latest Headlines</title>

  <style>
    :root {
      --navy: #101d35;
      --red: #d71920;
      --ink: #171a20;
      --muted: #687080;
      --line: #e5e7eb;
      --paper: #f4f5f7;
    }

    * { box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      margin: 0;
      background: var(--paper);
      color: var(--ink);
      font-family: Arial, Helvetica, sans-serif;
      line-height: 1.5;
    }

    a { color: inherit; text-decoration: none; }
    button, input, select, textarea { font: inherit; }

    .topline {
      background: #081326;
      color: #dfe6f1;
      padding: 7px 5%;
      font-size: 12px;
      display: flex;
      justify-content: space-between;
      gap: 12px;
    }

    header {
      background: var(--navy);
      color: white;
      padding: 20px 5% 0;
    }

    .brand-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 18px;
      padding-bottom: 17px;
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .logo {
      background: var(--red);
      font-weight: 900;
      font-size: 22px;
      padding: 8px 10px;
      color: white;
    }

    .brand h1 {
      font-size: clamp(20px, 3vw, 30px);
      line-height: 1.05;
      margin: 0;
      font-weight: 850;
    }

    .brand small {
      display: block;
      color: #c5cfdf;
      font-size: 11px;
      letter-spacing: 2px;
      margin-top: 5px;
    }

    .header-note {
      font-size: 12px;
      color: #c5cfdf;
      text-align: right;
    }

    nav {
      display: flex;
      overflow-x: auto;
      border-top: 1px solid #ffffff26;
    }

    nav button {
      white-space: nowrap;
      background: none;
      border: 0;
      border-bottom: 3px solid transparent;
      color: #eef2f8;
      padding: 13px 15px;
      cursor: pointer;
      font-size: 13px;
      font-weight: 700;
    }

    nav button:hover,
    nav button.active {
      background: #ffffff0d;
      border-bottom-color: var(--red);
    }

    .breaking {
      background: var(--red);
      color: white;
      display: flex;
      align-items: center;
      gap: 14px;
      padding: 10px 5%;
      font-size: 13px;
      font-weight: 700;
    }

    .breaking strong {
      background: white;
      color: var(--red);
      padding: 3px 7px;
      font-size: 10px;
    }

    main {
      max-width: 1200px;
      margin: 26px auto;
      padding: 0 22px;
    }

    .section-label {
      font-size: 12px;
      letter-spacing: 1.5px;
      font-weight: 800;
      text-transform: uppercase;
      margin: 0 0 13px;
      display: flex;
      align-items: center;
      gap: 9px;
    }

    .section-label::before {
      content: "";
      height: 17px;
      width: 4px;
      background: var(--red);
    }

    .search-row {
      display: flex;
      gap: 8px;
      margin-bottom: 20px;
    }

    .search-row input {
      flex: 1;
      min-width: 0;
      padding: 12px;
      border: 1px solid #d7dbe2;
      background: white;
    }

    .btn {
      background: var(--red);
      border: 0;
      color: white;
      padding: 11px 14px;
      font-weight: 800;
      cursor: pointer;
    }

    .btn:hover { background: #ad1017; }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.5fr 1fr;
      gap: 18px;
    }

    .hero {
      min-height: 350px;
      background:
        linear-gradient(0deg, #061326e8, #06132618),
        linear-gradient(135deg, #203b61, #7891a9);
      color: white;
      display: flex;
      align-items: end;
      padding: 26px;
      position: relative;
      overflow: hidden;
      cursor: pointer;
    }

    .hero::before {
      content: "UNICAL";
      position: absolute;
      top: 22px;
      right: 22px;
      font-size: clamp(42px, 8vw, 92px);
      font-weight: 900;
      color: #ffffff15;
    }

    .hero-content {
      position: relative;
      max-width: 650px;
    }

    .tag {
      display: inline-block;
      background: var(--red);
      color: white;
      font-size: 10px;
      font-weight: 800;
      text-transform: uppercase;
      padding: 5px 8px;
      margin-bottom: 12px;
    }

    .hero h2 {
      font-size: clamp(27px, 4vw, 43px);
      line-height: 1.1;
      margin: 0 0 12px;
    }

    .hero p {
      margin: 0;
      color: #e0e6ef;
      font-size: 13px;
    }

    .side-stack {
      display: grid;
      grid-template-rows: 1fr 1fr;
      gap: 18px;
    }

    .side-story {
      background: white;
      display: grid;
      grid-template-columns: 40% 1fr;
      min-height: 165px;
      overflow: hidden;
      border: 1px solid var(--line);
      cursor: pointer;
    }

    .story-art,
    .card-art {
      background: linear-gradient(135deg, #b8c6d9, #526985);
      display: flex;
      align-items: center;
      justify-content: center;
      color: #ffffffb8;
      font-size: 34px;
      font-weight: 900;
    }

    .story-art.red, .card-art.red {
      background: linear-gradient(135deg, #d71920, #76151c);
    }

    .story-art.gold, .card-art.gold {
      background: linear-gradient(135deg, #e7c06e, #94702f);
    }

    .story-art.green, .card-art.green {
      background: linear-gradient(135deg, #7eaf91, #294d40);
    }

    .card-art.purple {
      background: linear-gradient(135deg, #b5a5d3, #554574);
    }

    .side-copy { padding: 16px; }

    .side-copy h3 {
      font-size: 17px;
      line-height: 1.25;
      margin: 4px 0 9px;
    }

    .meta {
      font-size: 11px;
      color: var(--muted);
    }

    .content-layout {
      display: grid;
      grid-template-columns: minmax(0, 1fr) 300px;
      gap: 28px;
      margin-top: 34px;
    }

    .news-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 18px;
    }

    .news-card {
      background: white;
      border: 1px solid var(--line);
      overflow: hidden;
      display: flex;
      flex-direction: column;
      cursor: pointer;
      transition: transform .15s;
    }

    .news-card:hover { transform: translateY(-2px); }

    .card-art {
      height: 145px;
      font-size: 40px;
    }

    .card-body {
      padding: 16px;
      display: flex;
      flex-direction: column;
      flex: 1;
    }

    .card-body h3 {
      font-size: 19px;
      line-height: 1.25;
      margin: 8px 0;
    }

    .card-body p {
      font-size: 13px;
      color: #545c69;
      margin: 0 0 14px;
    }

    .card-body .meta { margin-top: auto; }

    .sidebar {
      display: flex;
      flex-direction: column;
      gap: 22px;
    }

    .panel {
      background: white;
      padding: 19px;
      border: 1px solid var(--line);
    }

    .panel h3 {
      font-size: 16px;
      margin: 0 0 13px;
      padding-bottom: 10px;
      border-bottom: 2px solid var(--navy);
    }

    .trend {
      display: flex;
      gap: 12px;
      padding: 12px 0;
      border-bottom: 1px solid var(--line);
      font-size: 13px;
      font-weight: 700;
      cursor: pointer;
    }

    .trend span {
      font-size: 23px;
      color: var(--red);
      font-weight: 900;
    }

    .newsletter p {
      font-size: 13px;
      color: var(--muted);
    }

    .newsletter input {
      width: 100%;
      padding: 11px;
      border: 1px solid var(--line);
      margin: 5px 0 9px;
    }

    .empty {
      display: none;
      background: white;
      padding: 24px;
      border: 1px solid var(--line);
      color: var(--muted);
    }

    footer {
      margin-top: 45px;
      background: #081326;
      color: #dfe6f1;
      padding: 32px 5%;
    }

    .footer-inner {
      max-width: 1200px;
      margin: auto;
      display: flex;
      justify-content: space-between;
      gap: 20px;
      flex-wrap: wrap;
    }

    .footer-inner strong {
      font-size: 18px;
      color: white;
    }

    .footer-inner p {
      font-size: 12px;
      color: #aebbd0;
      max-width: 520px;
    }

    .modal {
      display: none;
      position: fixed;
      inset: 0;
      background: #061326b8;
      z-index: 5;
      padding: 18px;
      overflow: auto;
      align-items: center;
      justify-content: center;
    }

    .modal.open { display: flex; }

    .modal-box {
      background: white;
      max-width: 720px;
      width: 100%;
      padding: 25px;
      position: relative;
    }

    .modal-box h2 {
      font-size: clamp(24px, 4vw, 36px);
      line-height: 1.15;
      margin: 10px 0;
    }

    .close {
      position: absolute;
      right: 14px;
      top: 10px;
      border: 0;
      background: #eef0f4;
      font-size: 22px;
      cursor: pointer;
    }

    .admin-fields { display: grid; gap: 12px; }

    .admin-fields input,
    .admin-fields select,
    .admin-fields textarea {
      width: 100%;
      padding: 11px;
      border: 1px solid #ccd2dc;
      margin-top: 5px;
    }

    .admin-fields textarea {
      min-height: 100px;
      resize: vertical;
    }

    .admin-open {
      background: transparent;
      color: #c5cfdf;
      border: 1px solid #64718a;
      padding: 8px 10px;
      cursor: pointer;
    }

    .notice {
      font-size: 12px;
      color: var(--muted);
    }

    @media (max-width: 800px) {
      .hero-grid, .content-layout {
        grid-template-columns: 1fr;
      }

      .hero { min-height: 310px; }

      .side-stack {
        grid-template-columns: 1fr 1fr;
        grid-template-rows: auto;
      }

      .side-story { grid-template-columns: 1fr; }
      .story-art { height: 105px; }

      .sidebar {
        display: grid;
        grid-template-columns: 1fr 1fr;
      }
    }

    @media (max-width: 560px) {
      .topline { padding: 7px 4%; font-size: 10px; }
      .header-note { display: none; }
      header { padding: 15px 4% 0; }
      .brand h1 { font-size: 20px; }
      nav button { padding: 12px 11px; font-size: 12px; }
      .breaking { padding: 9px 4%; font-size: 11px; }
      main { padding: 0 13px; margin-top: 18px; }
      .hero { min-height: 310px; padding: 20px; }
      .hero h2 { font-size: 29px; }
      .side-stack { grid-template-columns: 1fr; }
      .side-story { grid-template-columns: 36% 1fr; min-height: 130px; }
      .story-art { height: auto; }
      .side-copy { padding: 12px; }
      .side-copy h3 { font-size: 15px; }
      .news-grid { grid-template-columns: 1fr; }
      .card-art { height: 165px; }
      .sidebar { grid-template-columns: 1fr; }
      .search-row { flex-wrap: wrap; }
      .search-row input { flex-basis: 100%; }
    }
  </style>
</head>

<body>
  <div class="topline">
    <span id="today">LATEST HEADLINES · UNICAL AND BEYOND</span>
    <span>INFORMING OUR COMMUNITY</span>
  </div>

  <header>
    <div class="brand-row">
      <a class="brand" href="#">
        <span class="logo">UN</span>
        <span>
          <h1>UNICAL NEWS UPDATE</h1>
          <small>CAMPUS · COMMUNITY · COUNTRY</small>
        </span>
      </a>
      <div class="header-note">
        Your daily source for campus<br>and national headlines
      </div>
    </div>

    <nav id="nav">
      <button class="active" data-category="All">HOME</button>
      <button data-category="UNICAL Campus">UNICAL CAMPUS</button>
      <button data-category="Education">EDUCATION</button>
      <button data-category="Nigeria">NIGERIA</button>
      <button data-category="Politics">POLITICS</button>
      <button data-category="Sports">SPORTS</button>
      <button data-category="Entertainment">ENTERTAINMENT</button>
    </nav>
  </header>

  <div class="breaking">
    <strong>BREAKING</strong>
    <span>UNICAL News Update — bringing campus stories and important headlines into focus.</span>
  </div>

  <main>
    <div class="search-row">
      <input id="search" type="search"
        placeholder="Search headlines and stories..."
        aria-label="Search news">
      <button class="btn" id="searchBtn">SEARCH</button>
    </div>

    <section>
      <h2 class="section-label">Top Stories</h2>

      <div class="hero-grid">
        <article class="hero" id="heroStory" tabindex="0" role="button">
          <div class="hero-content">
            <span class="tag">EDITOR'S PICK</span>
            <h2 id="heroTitle">UNICAL News Update: the stories shaping campus life</h2>
            <p id="heroSummary">Campus updates, education news and important developments — all in one place.</p>
            <p class="meta" id="heroMeta" style="color:#cbd5e1;margin-top:14px">
              UNICAL News Update · Sample homepage story
            </p>
          </div>
        </article>

        <div class="side-stack" id="sideStories"></div>
      </div>
    </section>

    <div class="content-layout">
      <section>
        <h2 class="section-label" id="latestHeading">Latest News</h2>
        <div class="news-grid" id="newsGrid"></div>
        <div class="empty" id="empty">
          No stories match your search. Try another keyword or category.
        </div>
      </section>

      <aside class="sidebar">
        <div class="panel">
          <h3>Most Read</h3>
          <div id="trending"></div>
        </div>

        <div class="panel newsletter">
          <h3>Get the Headlines</h3>
          <p>Join the reader list for updates from UNICAL News Update.</p>
          <form id="newsletterForm">
            <input type="email" id="email"
              placeholder="Your email address" required>
            <button class="btn" type="submit">SIGN ME UP</button>
          </form>
          <p id="newsletterMsg" class="notice">
            Demo form only — connect an email service to collect subscriptions.
          </p>
        </div>

        <div class="panel">
          <h3>About This Site</h3>
          <p style="font-size:13px;color:#5d6572">
            A news layout for campus and community reporting.
            Verify facts and add a source before publishing real news.
          </p>
        </div>
      </aside>
    </div>
  </main>

  <footer>
    <div class="footer-inner">
      <div>
        <strong>UNICAL NEWS UPDATE</strong>
        <p>Campus · Community · Country. Original branding inspired by modern news layouts.</p>
      </div>
      <div>
        <p>Contact: editor@unicalnewsupdate.example</p>
        <p>© <span id="year"></span> UNICAL News Update. Demo website.</p>
        <button class="admin-open" id="openAdmin">EDITOR / ADMIN</button>
      </div>
    </div>
  </footer>

  <div class="modal" id="articleModal" role="dialog" aria-modal="true">
    <div class="modal-box">
      <button class="close" data-close="articleModal">×</button>
      <span class="tag" id="articleCategory">NEWS</span>
      <h2 id="articleTitle"></h2>
      <p class="meta" id="articleMeta"></p>
      <p id="articleBody" style="white-space:pre-line"></p>
      <p class="notice">
        Replace sample content with verified reporting and clearly identify sources.
      </p>
    </div>
  </div>

  <div class="modal" id="adminModal" role="dialog" aria-modal="true">
    <div class="modal-box">
      <button class="close" data-close="adminModal">×</button>
      <span class="tag">LOCAL DEMO EDITOR</span>
      <h2>Publish a story</h2>
      <p class="notice">
        Stories added here only appear in this browser session.
        This demo has no secure login or shared database.
      </p>

      <form id="publishForm" class="admin-fields">
        <label>
          Headline
          <input id="newTitle" required maxlength="140"
            placeholder="Enter a clear headline">
        </label>

        <label>
          Category
          <select id="newCategory">
            <option>UNICAL Campus</option>
            <option>Education</option>
            <option>Nigeria</option>
            <option>Politics</option>
            <option>Sports</option>
            <option>Entertainment</option>
          </select>
        </label>

        <label>
          Short summary
          <textarea id="newSummary" required maxlength="260"
            placeholder="A short introduction"></textarea>
        </label>

        <label>
          Full article
          <textarea id="newBody" required
            placeholder="Write the article and include verified sources"></textarea>
        </label>

        <label>
          Reporter / source
          <input id="newAuthor" required placeholder="Reporter name or source">
        </label>

        <button class="btn" type="submit">PUBLISH STORY</button>
        <div id="publishMsg" class="notice"></div>
      </form>
    </div>
  </div>

  <script>
    const stories = [
      {
        id: 1,
        category: "UNICAL Campus",
        title: "UNICAL News Update: the stories shaping campus life",
        summary: "Campus updates, student voices and community developments in one place.",
        body: "Welcome to UNICAL News Update. This is demonstration copy. Replace it with a verified report, date and reliable sources before publishing.",
        author: "Editorial Desk",
        style: "",
        mark: "UN",
        date: "Sample story"
      },
      {
        id: 2,
        category: "Education",
        title: "What students should know about academic announcements",
        summary: "A guide to keeping track of official notices, schedules and academic information.",
        body: "Confirm academic information through official university channels. Add the verified announcement, dates and source before publishing.",
        author: "Education Desk",
        style: "gold",
        mark: "EDU",
        date: "Sample story"
      },
      {
        id: 3,
        category: "Nigeria",
        title: "Community voices: local issues worth following",
        summary: "Useful community reporting, public-interest updates and local perspectives.",
        body: "A real report should include confirmed facts, relevant context and responses from the people or organisations involved.",
        author: "News Desk",
        style: "red",
        mark: "NG",
        date: "Sample story"
      },
      {
        id: 4,
        category: "UNICAL Campus",
        title: "Student life: clubs, events and opportunities on campus",
        summary: "Highlighting activities, student organisations and opportunities around the university.",
        body: "Confirm event date, venue, organisers, registration details and any changes before posting.",
        author: "Campus Desk",
        style: "green",
        mark: "UNI",
        date: "Sample story"
      },
      {
        id: 5,
        category: "Politics",
        title: "Explainer: public decisions that affect students",
        summary: "Breaking down public policy and explaining why it matters to young people.",
        body: "A good explainer separates confirmed facts from opinion and links to primary sources.",
        author: "Politics Desk",
        style: "purple",
        mark: "POL",
        date: "Sample story"
      },
      {
        id: 6,
        category: "Sports",
        title: "Sports desk: results, fixtures and standout performances",
        summary: "A home for sports news, match reports and updates.",
        body: "Add confirmed match details, dates, competition names and source links.",
        author: "Sports Desk",
        style: "green",
        mark: "SPT",
        date: "Sample story"
      },
      {
        id: 7,
        category: "Entertainment",
        title: "Entertainment and culture: stories people are talking about",
        summary: "Covering music, film, culture and creative work.",
        body: "Add confirmed details, attribution and relevant context before publishing.",
        author: "Culture Desk",
        style: "purple",
        mark: "ART",
        date: "Sample story"
      }
    ];

    let selectedCategory = "All";
    let nextId = 8;

    const $ = id => document.getElementById(id);

    function safe(value) {
      return String(value).replace(/[&<>"']/g, character => ({
        "&": "&amp;",
        "<": "&lt;",
        ">": "&gt;",
        '"': "&quot;",
        "'": "&#39;"
      })[character]);
    }

    function openArticle(story) {
      $("articleCategory").textContent = story.category;
      $("articleTitle").textContent = story.title;
      $("articleMeta").textContent =
        story.author + " · " + story.date;
      $("articleBody").textContent = story.body;
      $("articleModal").classList.add("open");
    }

    function card(story) {
      return `
        <article class="news-card" tabindex="0" role="button"
          data-id="${story.id}" aria-label="Read ${safe(story.title)}">
          <div class="card-art ${safe(story.style)}">
            ${safe(story.mark || "NEWS")}
          </div>
          <div class="card-body">
            <span class="tag" style="align-self:flex-start">
              ${safe(story.category)}
            </span>
            <h3>${safe(story.title)}</h3>
            <p>${safe(story.summary)}</p>
            <div class="meta">
              ${safe(story.author)} · ${safe(story.date)}
            </div>
          </div>
        </article>
      `;
    }

    function render() {
      const query = $("search").value.trim().toLowerCase();

      const filtered = stories.filter(story => {
        const categoryMatches =
          selectedCategory === "All" ||
          story.category === selectedCategory;

        const text = (
          story.title + " " +
          story.summary + " " +
          story.category + " " +
          story.body
        ).toLowerCase();

        return categoryMatches && (!query || text.includes(query));
      });

      const top = stories[0];

      $("heroTitle").textContent = top.title;
      $("heroSummary").textContent = top.summary;
      $("heroMeta").textContent = top.author + " · " + top.date;

      $("sideStories").innerHTML = stories.slice(1, 3).map(story => `
        <article class="side-story" tabindex="0" role="button"
          data-id="${story.id}">
          <div class="story-art ${safe(story.style)}">
            ${safe(story.mark)}
          </div>
          <div class="side-copy">
            <span class="meta">${safe(story.category)}</span>
            <h3>${safe(story.title)}</h3>
            <span class="meta">${safe(story.author)}</span>
          </div>
        </article>
      `).join("");

      $("newsGrid").innerHTML = filtered.map(card).join("");
      $("empty").style.display = filtered.length ? "none" : "block";

      $("latestHeading").textContent =
        selectedCategory === "All"
          ? "Latest News"
          : selectedCategory + " News";

      $("trending").innerHTML = stories.slice(0, 4).map((story, index) => `
        <div class="trend" tabindex="0" role="button"
          data-id="${story.id}">
          <span>0${index + 1}</span>
          <div>
            ${safe(story.title)}
            <div class="meta">${safe(story.category)}</div>
          </div>
        </div>
      `).join("");

      document.querySelectorAll("[data-id]").forEach(element => {
        element.onclick = () => {
          const story = stories.find(
            item => item.id === Number(element.dataset.id)
          );
          if (story) openArticle(story);
        };

        element.onkeydown = event => {
          if (event.key === "Enter" || event.key === " ") {
            event.preventDefault();
            element.click();
          }
        };
      });
    }

    $("nav").addEventListener("click", event => {
      const button = event.target.closest("button[data-category]");
      if (!button) return;

      selectedCategory = button.dataset.category;

      document.querySelectorAll("nav button").forEach(item => {
        item.classList.toggle("active", item === button);
      });

      render();
    });

    $("searchBtn").onclick = render;
    $("search").addEventListener("input", render);

    $("search").addEventListener("keydown", event => {
      if (event.key === "Enter") render();
    });

    $("heroStory").onclick = () => openArticle(stories[0]);

    $("heroStory").onkeydown = event => {
      if (event.key === "Enter") openArticle(stories[0]);
    };

    document.querySelectorAll("[data-close]").forEach(button => {
      button.onclick = () => {
        $(button.dataset.close).classList.remove("open");
      };
    });

    document.querySelectorAll(".modal").forEach(modal => {
      modal.addEventListener("click", event => {
        if (event.target === modal) {
          modal.classList.remove("open");
        }
      });
    });

    document.addEventListener("keydown", event => {
      if (event.key === "Escape") {
        document.querySelectorAll(".modal").forEach(modal => {
          modal.classList.remove("open");
        });
      }
    });

    $("openAdmin").onclick = () => {
      $("adminModal").classList.add("open");
    };

    $("publishForm").addEventListener("submit", event => {
      event.preventDefault();

      const category = $("newCategory").value;

      const story = {
        id: nextId++,
        category,
        title: $("newTitle").value.trim(),
        summary: $("newSummary").value.trim(),
        body: $("newBody").value.trim(),
        author: $("newAuthor").value.trim(),
        style: "red",
        mark: category.split(" ")
          .map(word => word[0]).join("").slice(0, 4).toUpperCase(),
        date: new Date().toLocaleDateString()
      };

      stories.unshift(story);
      selectedCategory = "All";

      document.querySelectorAll("nav button").forEach(button => {
        button.classList.toggle(
          "active", button.dataset.category === "All"
        );
      });

      $("search").value = "";
      render();

      $("publishMsg").textContent =
        "Story added to this browser session.";

      event.target.reset();
    });

    $("newsletterForm").addEventListener("submit", event => {
      event.preventDefault();

      $("newsletterMsg").textContent =
        "Thanks! This is a demo — no email was stored or sent.";

      event.target.reset();
    });

    const now = new Date();

    $("today").textContent =
      now.toLocaleDateString(undefined, {
        weekday: "long",
        year: "numeric",
        month: "long",
        day: "numeric"
      }).toUpperCase() + " · LATEST HEADLINES";

    $("year").textContent = now.getFullYear();

    render();
  </script>
</body>
</html>
