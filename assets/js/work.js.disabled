const works = [

    {
        id: 1,
        title: "🚀 India's Toll Revolution is Here! | MLFF Explained",
        type: "short",
        duration: "1:18",
        youtubeId: "oBzVREBxCpw",
    },


    {
        id: 2,
        title: "🩸 Your Blood Generates Electricity? ⚡How Glucometers Detect Glucose!",
        type: "short",
        duration: "1:01",
        youtubeId: "EgpoaXXQWSM",
    },

    {
        id: 3,
        title: "How Remotes Talk to Devices 🤯📡 (Infrared Technology)",
        type: "short",
        duration: "1:08",
        youtubeId: "rQOOx0W1aGY",
    },

    {
        id: 4,
        title: "Why do Cricket Stumps light up? 🧐🏏",
        type: "short",
        duration: "0:58",
        youtubeId: "86iRPcQyMNo",
    },

    {
        id: 5,
        title: "How Wireless Charging ⚡ Actually Works? No Cable Needed!",
        type: "short",
        duration: "1:07",
        youtubeId: "QsRKmC2EaF4",
    },

    {
        id: 6,
        title: "Why No One Can Read Your Messages 👀",
        type: "short",
        duration: "1:14",
        youtubeId: "1wXuRhnGDVU",
    },

    {
        id: 7,
        title: "How Air Purifier Works? | Clean Air at Home 🌬",
        type: "short",
        duration: "1:44",
        youtubeId: "ei5M1Ep7EmU",
    }

];

const grid = document.getElementById("fw-grid");
const loadMoreBtn = document.getElementById("fw-load-more");

const CARDS_PER_LOAD = 3;

let visibleCards = CARDS_PER_LOAD;

let currentFilter = "all";

const filterButtons = document.querySelectorAll(".fw-filter-btn");

function createCard(work) {

    const videoUrl =
        work.type === "short"
            ? `https://www.youtube.com/shorts/${work.youtubeId}`
            : `https://www.youtube.com/watch?v=${work.youtubeId}`;

    const thumbnailUrl =
        `https://i.ytimg.com/vi/${work.youtubeId}/hqdefault.jpg`;

    return `
        <div class="fw-card">

            <a href="${videoUrl}" target="_blank" rel="noopener noreferrer">

                <div class="fw-thumbnail">

                    <img src="${thumbnailUrl}" alt="${work.title}" loading="lazy">

                    <div class="fw-play">
                        ▶
                    </div>

                    <span class="fw-duration">
                        ${work.duration}
                    </span>

                </div>

                <div class="fw-content">

                    <h3 class="fw-title">
                        ${work.title}
                    </h3>

                    <span class="fw-type">
                        ${work.platform ?? "YouTube Short"}
                    </span>

                </div>

            </a>

        </div>
    `;
}

function renderWorks() {

    const filteredWorks =
        currentFilter === "all"
            ? works
            : works.filter(work => work.type === currentFilter);

    const visibleWorks = filteredWorks.slice(0, visibleCards);

    grid.innerHTML = visibleWorks
        .map(createCard)
        .join("");

    if (visibleCards >= filteredWorks.length) {
        loadMoreBtn.style.display = "none";
    } else {
        loadMoreBtn.style.display = "inline-flex";
    }

}

loadMoreBtn.addEventListener("click", () => {

    visibleCards += CARDS_PER_LOAD;

    renderWorks();

});

filterButtons.forEach(button => {

    button.addEventListener("click", () => {

        filterButtons.forEach(btn =>
            btn.classList.remove("active")
        );

        button.classList.add("active");

        currentFilter = button.dataset.filter;

        visibleCards = CARDS_PER_LOAD;

        renderWorks();

    });

});

renderWorks();