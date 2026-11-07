
// Select all sidebar navigation links
const navLinks = document.querySelectorAll(".nav-link");

// Select the dashboard content
const mainContent = document.querySelector(".main");

// Add click event to each navigation link
navLinks.forEach(link => {

    link.addEventListener("click", function(event) {

        event.preventDefault();

        const toolName = this.textContent.trim();

        // Remove active class from all links
        navLinks.forEach(nav => nav.classList.remove("active"));

        // Add active class to clicked link
        this.classList.add("active");

        // Dashboard button
        if (toolName.includes("Dashboard")) {
            location.reload();
            return;
        }

        // Show Coming Soon message
        mainContent.innerHTML = `
            <div style="
                display:flex;
                justify-content:center;
                align-items:center;
                min-height:70vh;
                text-align:center;
            ">

                <div>
                    <h1 style="
                        font-size:32px;
                        color:#596ce5;
                        margin-bottom:15px;
                    ">
                        🚀 Coming Soon!
                    </h1>

                    <h2 style="
                        color:#20283b;
                        margin-bottom:12px;
                    ">
                        ${toolName}
                    </h2>

                    <p style="
                        color:#8490a5;
                        font-size:15px;
                    ">
                        We are working on this feature.
                        Stay tuned!
                    </p>

                    <button onclick="location.reload()" style="
                        margin-top:25px;
                        padding:12px 25px;
                        background:#596ce5;
                        color:white;
                        border:none;
                        border-radius:8px;
                        cursor:pointer;
                        font-size:14px;
                    ">
                        ← Back to Dashboard
                    </button>
                </div>

            </div>
        `;

    });

});
