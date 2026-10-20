                        <h3>Caption Generator</h3>
                <p>Write engaging captions for your posts.</p>
            </button>

            <button class="tool mint"
                onclick="selectTool('hashtags',this)">
                <div class="tool-icon">#️⃣</div>
                <h3>Hashtag Ideas</h3>
                <p>Find relevant hashtags for your posts.</p>
            </button>

            <button class="tool lavender"
                onclick="selectTool('reels',this)">
                <div class="tool-icon">🎬</div>
                <h3>Reel Ideas</h3>
                <p>Get creative video concepts and scripts.</p>
            </button>

            <button class="tool peach"
                onclick="selectTool('product',this)">
                <div class="tool-icon">🛍️</div>
                <h3>Product Description</h3>
                <p>Describe your products with style.</p>
            </button>

            <button class="tool blue"
                onclick="selectTool('festival',this)">
                <div class="tool-icon">🎉</div>
                <h3>Festival Marketing</h3>
                <p>Create festive promotional content.</p>
            </button>

            <button class="tool cyan"
                onclick="selectTool('bio',this)">
                <div class="tool-icon">👤</div>
                <h3>Instagram Bio</h3>
                <p>Write a catchy profile description.</p>
            </button>

        </div>
    </section>

    <section id="generator" class="generator">

        <div class="generator-heading">
            <div class="generator-icon">✍️</div>
            <div>
                <h2 id="formTitle">Caption Generator</h2>
                <p>Create content for your social media posts.</p>
            </div>
        </div>

        <div class="generator-grid">

            <div>
                <div class="form-group">
                    <label for="business">🏪 Business or page name</label>
                    <input id="business" placeholder="e.g. Elva Jewels">
                </div>

                <div class="form-group">
                    <label for="topic">📝 What is your content about?</label>
                    <textarea id="topic" maxlength="500"
                        placeholder="e.g. Beautiful 92.5 silver necklace"></textarea>
                </div>

                <div class="select-row">
                    <div class="form-group">
                        <label for="audience">👥 Target audience</label>
                        <select id="audience">
                            <option value="everyone">Everyone</option>
                            <option value="customers">Potential customers</option>
                            <option value="young people">Young people</option>
                            <option value="business owners">Business owners</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label for="language">🌐 Language</label>
                        <select id="language">
                            <option value="English">English</option>
                            <option value="Hindi">Hindi</option>
                            <option value="Hinglish">Hinglish</option>
                        </select>
                    </div>
                </div>

                <div class="form-group">
                    <label for="tone">🎨 Writing style</label>
                    <select id="tone">
                        <option value="engaging">Engaging</option>
                        <option value="professional">Professional</option>
                        <option value="fun">Fun and trendy</option>
                        <option value="premium">Premium</option>
                    </select>
                </div>

                <button class="generate" onclick="generateContent()">
                    ✨ Generate Content
                </button>

                <p class="small-note">
                    Demo version: this uses templates, not a live AI model.
                </p>
            </div>

            <div class="output-card">
                <div class="output-top">
                    <h3>✨ Your Content</h3>

                    <div class="output-actions">
                        <button class="secondary" onclick="copyContent()">
                            📋 Copy
                        </button>
                        <button class="secondary" onclick="shareContent()">
                            ↗ Share
                        </button>
                    </div>
                </div>

                <div id="resultText" class="result-text" aria-live="polite">Your generated content will appear here.

💡 Choose a tool, enter a topic, and tap Generate Content.</div>

                <div class="hint">
                    💡 Personalise your content before publishing it.
                </div>
            </div>

        </div>
    </section>

    <section id="pricing">
        <div class="section-heading">
            <h2>Simple Plans for Everyone</h2>
            <p>Example plans for a future version of SocialBoost AI.</p>
        </div>

        <div class="pricing-grid">

            <div class="price-card">
                <h3>Free</h3>
                <div class="price">₹0 <small>/ forever</small></div>
                <p>For trying the tools.</p>
                <ul>
                    <li>Caption templates</li>
                    <li>Hashtag suggestions</li>
                    <li>Reel ideas</li>
                    <li>Copy and share</li>
                </ul>
            </div>

            <div class="price-card featured">
                <h3>⭐ Pro</h3>
                <div class="price">₹299 <small>/ month</small></div>
                <p>Proposed pricing; not active.</p>
                <ul>
                    <li>Planned AI generation</li>
                    <li>Additional content tools</li>
                    <li>More usage</li>
                    <li>More languages</li>
                </ul>
            </div>

            <div class="price-card">
                <h3>Business</h3>
                <div class="price">₹799 <small>/ month</small></div>
                <p>Proposed pricing; not active.</p>
                <ul>
                    <li>Planned business features</li>
                    <li>Expanded content tools</li>
                    <li>Higher usage limits</li>
                    <li>Marketing templates</li>
                </ul>
            </div>

        </div>

        <p class="small-note">
            Payment collection, user accounts, and premium access are not
            implemented in this prototype.
        </p>
    </section>

</main>

<footer id="about">
    <div class="footer-inner">
        <div class="brand">
            <div class="brand-icon">🌿</div>
            <div>
                SocialBoost <span>AI</span>
                <small>Smart Tools. Real Growth.</small>
            </div>
        </div>

        <div class="footer-text">
            💜 Built for creators and small businesses.
        </div>

        <div class="footer-text">
            © <span id="year"></span> SocialBoost AI
        </div>
    </div>
</footer>

<script>
let currentTool = "caption";

document.getElementById("year").textContent =
    new Date().getFullYear();

const toolNames = {
    caption: "Caption Generator",
    hashtags: "Hashtag Ideas",
    reels: "Reel Ideas",
    product: "Product Description",
    festival: "Festival Marketing",
    bio: "Instagram Bio"
};

function scrollToGenerator() {
    document.getElementById("generator").scrollIntoView({
        behavior: "smooth",
        block: "start"
    });
}

function selectTool(tool, element) {
    currentTool = tool;

    document.querySelectorAll(".tool").forEach(button => {
        button.classList.remove("active");
    });

    element.classList.add("active");

    document.getElementById("formTitle").textContent =
        toolNames[tool];

    scrollToGenerator();
}

function generateContent() {
    const business =
        document.getElementById("business").value.trim()
        || "Our Brand";

    const topic =
        document.getElementById("topic").value.trim();

    const audience =
        document.getElementById("audience").value;

    const language =
        document.getElementById("language").value;

    const tone =
        document.getElementById("tone").value;

    if (!topic) {
        alert("Please enter a topic first!");
        document.getElementById("topic").focus();
        return;
    }

    const result = createTemplate({
        tool: currentTool,
        business,
        topic,
        audience,
        language,
        tone
    });

    document.getElementById("resultText").textContent = result;
}

function createTemplate(data) {
    const {
        tool,
        business,
        topic,
        audience,
        language,
        tone
    } = data;

    let output = "";

    if (tool === "hashtags") {
        output =
`${business} | Hashtag Ideas

${topic}

#Instagram #ContentCreator #SmallBusiness
#ExplorePage #NewPost #Trending
#OnlineShopping #DiscoverMore

Tip: Use hashtags relevant to your actual post.`;

    } else if (tool === "reels") {
        output =
`🎬 REEL IDEA FOR ${business}

Topic: ${topic}

1. THE HOOK
Start with: "Wait until you see this!"

2. SHOW
Present ${topic} in an interesting way.

3. ADD DETAILS
Highlight one useful feature or interesting detail.

4. CALL TO ACTION
"Save this Reel and share it with a friend!"

✨ Try clear lighting, close-up shots and readable text.`;

    } else if (tool === "product") {
        output =
`${business} ✨

Discover ${topic}.

Thoughtfully presented and ready to be showcased to your customers.

WHY EXPLORE IT?

✦ Attractive presentation
✦ A thoughtful gifting option
✦ A style to explore for different occasions

📩 Contact us for product details, availability and pricing.

#ProductDetails #Shopping #DiscoverMore`;

    } else if (tool === "festival") {
        output =
`🎉 FESTIVE GREETINGS FROM ${business.toUpperCase()}!

Celebrate the season with ${topic}.

Make every moment special with something meaningful.

✨ Explore our collection.
🎁 Discover thoughtful gifting ideas.
💌 Message us for more information.

#FestiveSeason #FestivalVibes #SmallBusiness`;

    } else if (tool === "bio") {
        output =
`${business} ✨

${topic}

✦ Quality | Style | Customer Care
✦ Discover something special
📩 DM for enquiries

Edit these lines to accurately represent your business.`;

    } else {
        const captions = {
            engaging:
`✨ Something special is here!

Discover ${topic} with ${business}.

Save this post and tell us what you think! 💜

#DiscoverMore #InstagramPost #NewCollection`,

            professional:
`${business}

Explore ${topic} with a focus on thoughtful presentation and customer experience.

Contact us for more information.

#Business #Quality #CustomerExperience`,

            fun:
`POV: You just discovered ${topic} 👀✨

Add this to your list and share it with someone who needs to see it!

#Trending #ReelIdeas #DiscoverMore`,

            premium:
`${business} presents ${topic}.

Thoughtfully selected. Beautifully presented. Made to make an impression.

Discover more by contacting our team.

#PremiumStyle #TimelessDesign #DetailsMatter`
        };

        output = captions[tone] || captions.engaging;

        if (audience === "young people") {
            output += "\n\nMade for your next favourite discovery. ✨";
        }
    }

    if (language === "Hindi") {
        output +=
"\n\nNote: This demo currently creates English templates. Real Hindi generation requires an AI or translation service.";
    } else if (language === "Hinglish") {
        output +=
"\n\nNote: Hinglish generation requires an AI or translation service.";
    }

    return output;
}

async function copyContent() {
    const text =
        document.getElementById("resultText").textContent;

    try {
        await navigator.clipboard.writeText(text);
        alert("✨ Content copied successfully!");
    } catch (error) {
        const area = document.createElement("textarea");
        area.value = text;
        document.body.appendChild(area);
        area.select();

        try {
            document.execCommand("copy");
            alert("Content copied!");
        } catch (copyError) {
            alert("Please select and copy the text manually.");
        }

        area.remove();
    }
}

async function shareContent() {
    const text =
        document.getElementById("resultText").textContent;

    if (navigator.share) {
        try {
            await navigator.share({
                title: "SocialBoost AI",
                text: text
            });
        } catch (error) {
            // User cancelled sharing.
        }
    } else {
        await copyContent();
    }
}
</script>

</body>
</html>
