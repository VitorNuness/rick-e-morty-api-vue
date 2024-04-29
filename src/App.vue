<template>
    <header>
        <nav class="navbar navbar-expand-lg">
            <div class="container">
                <router-link class="navbar-brand" aria-current="page" to="/">
                    <img
                        src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b1/Rick_and_Morty.svg/2560px-Rick_and_Morty.svg.png"
                        alt="Rick and Morth logo"
                        width="150rem"
                    />
                </router-link>
                <button
                    class="navbar-toggler"
                    type="button"
                    data-bs-toggle="collapse"
                    data-bs-target="#navbarNav"
                    aria-controls="navbarNav"
                    aria-expanded="false"
                    aria-label="Toggle navigation"
                >
                    <span class="navbar-toggler-icon"></span>
                </button>
                <div class="collapse navbar-collapse" id="navbarNav">
                    <ul class="navbar-nav">
                        <li class="nav-item">
                            <router-link
                                class="nav-link"
                                aria-current="page"
                                to="/"
                            >
                                Início
                            </router-link>
                        </li>
                        <li class="nav-item">
                            <router-link
                                class="nav-link"
                                aria-current="page"
                                to="/about"
                            >
                                Sobre
                            </router-link>
                        </li>
                    </ul>
                </div>
            </div>
        </nav>
    </header>
    <main>
        <router-view></router-view>
    </main>

    <footer>
        <div>Unimar | ADS | {{ new Date().getFullYear() }}</div>
    </footer>
</template>

<style>
body::-webkit-scrollbar {
    width: 8px;
}

body::-webkit-scrollbar-track {
    background: #fff; /* color of the tracking area */
}

body::-webkit-scrollbar-thumb {
    background-color: #0fa7ff; /* color of the scroll thumb */
    border: 2px solid #5bff0f;
    border-radius: 20px; /* roundness of the scroll thumb */
}

.nav-link {
    color: #0fa7ff;
    text-shadow: 1px 1px 1px #5bff0f;
}

main {
    padding: 10px;
}

footer {
    /* background: linear-gradient(transparent, #fff 50%); */
    background: #fff;
    box-shadow: -1px 0 4px #5bff0f;
    position: fixed;
    bottom: 0;
    width: 100%;
    height: 80px;
    display: flex;
    align-items: end;
    justify-content: center;
    padding-bottom: 20px;
}
</style>
