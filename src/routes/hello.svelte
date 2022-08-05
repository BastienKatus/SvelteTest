<script>
    import HelloWorld from "$lib/HelloWorld.svelte";
</script>

<style>
    :root{
        --grey : #807c7c ;
        --grey-mat: #dddbd8;
        --light-blue: #39c2ef ;
    }

    h1, h2, h3{
        display: flex;
        margin: 50px auto 12px auto;
        border-bottom: 1px solid var(--light-blue);
        width: fit-content;
    }

    h3{
        margin: 50px auto 12px 15%;
    }

    p {
        text-align: justify;
        margin: 0 auto;
        padding:0 15%;
    }

    ul {
        padding: 0;
        font-size: 1.1em;
        margin: 0 auto 0 auto;
    }

    .navbar {
        background-color: var(--grey);
        padding: 60px;
        text-align: center;
        margin: 0 auto;
    }

    .navbar li {
        display: inline-block;
        min-width: 200px;
        width: 15%;
        margin: 0 auto 0 auto;
    }

    .navbar a {
        color: var(--grey);
        text-decoration: none;
        font-weight: 100;
        font-size: 22px;
        text-transform: uppercase;
        text-shadow: 1px 1px 1px #000;
    }

    .navbar a:hover {
        color: var(--grey-mat);
        transition: 1s all;
    }

    footer {
        display: flex;
        justify-content: center;
        margin-top: 32px;
        padding: 5%;
        background-color: var(--grey);
    }
</style>

<main>
    <nav class="navbar">
        <ul>
            <li>
                <a href="#lecture">Lecture des consignes</a>
            </li>
            <li>
                <a href="#get_started">Lancement du projet</a>
            </li>
            <li>
                <a href="#code">Partie code et réalisation du test</a>
            </li>
            <li>
                <a href="#questions">Questions diverses</a>
            </li>
        </ul>
    </nav>


    <section id="doc">
        <h1 class="font-medium leading-tight text-5xl mt-0 mb-2 text-blue-600"> Document de rendu </h1>
    </section>

    <section id="lecture">
        <h2 class="font-medium leading-tight text-4xl mt-0 mb-2 text-blue-600">Lecture des consignes</h2>
        <p>Fiche de note et procédure appliqués pour réaliser le test.</p>
    </section>

    <section id="get_started">
        <h2 class="font-medium leading-tight text-4xl mt-0 mb-2 text-blue-600">Récupération / Préparation / Premier lancement du projet</h2>
        <p>Erreur lors du lancement du projet. La commande « npm i » s’exécute et lance une erreur.</p>
        <p>Solution : upgrade Node de version (doit être supérieur à 16.9 pour lancer svelte kit)</p>
    </section>

    <section id="code">
        <h2 class="font-medium leading-tight text-4xl mt-0 mb-2 text-blue-600">Partie code et réalisation du test</h2>
        <p>Après avoir analysé et regarder les différents composants, je me lance dans la résolution des premières questions.</p>
        <ul>
            <li>
                <h3 class="font-medium leading-tight text-xl mt-0 mb-2 text-blue-600">Value Integer</h3>
                <p>RAS</p>
            </li>
            <li>
                <h3 class="font-medium leading-tight text-xl mt-0 mb-2 text-blue-600">Value Décimal</h3>
                <p>
                    Reprise d’éléments du composant précédant.
                    Afin de tronquée la valeur entrée par l’utilisateur, la solution retenue a été de convertir la valeur en String afin de découper la chaine avec le caractère «. ». Si cela est possible alors c’est un nombre décimal. Ensuite, on sélectionne les premiers caractères de la chaîne jusqu’à en avoir autant que la précision.
                    On concatène et affiche la valeur tronquée. Cette solution est dynamique et peut s’adapter sans toucher le code dans le cas où la précision changerait.
                </p>
            </li>
            <li>
                <h3 class="font-medium leading-tight text-xl mt-0 mb-2 text-blue-600">Value Boolean</h3>
                <p>Récupération des templates des composants existants. Adaptation pour gérer une checkbox et pour afficher la valeur récupérer depuis les données.</p>
            </li>
            <li>
                <h3 class="font-medium leading-tight text-xl mt-0 mb-2 text-blue-600">Value Time</h3>
                <p>Création du composant ValueTime en prenant pour exemple le composant ValueDateTime. Affichage de la valeur récupérer depuis l’API.</p>
            </li><li>
                <h3 class="font-medium leading-tight text-xl mt-0 mb-2 text-blue-600">Value DateTime</h3>
                <p>
                    Pouvez-vous expliquer ce que l'on cherche à faire dans la fonction handleChange du composant ValueDateTime?
                    Dans la fonction handleChange de ValueDateTime, tout d’abords on récupère la date entrée par l’utilisateur. Ensuite, on va récupérer deux informations au sujet de la date de l’utilisateur. Tout d’abord on récupère la date (le timestamp) en sélectionnant la date en fonction du fuseau horaire. 
                    Dans le second temps, on prend le timestamp de l’utilisateur sans prendre en compte les changements de fuseaux horaires, puis on soustrait le timestamp possédant le décalage de fuseau horaire de l’utilisateur en l’ayant convertit en milliseconde.
                    Enfin on recrée la date sous format ISO.
                    La dernière instruction permet de récupérer une date précisée à la minute.
                </p>
            </li>
        </ul>
    </section>

    <section id="questions">
        <h2 class="font-medium leading-tight text-4xl mt-0 mb-2 text-blue-600">Questions diverses</h2>
        <h3 class="font-medium leading-tight text-xl mt-0 mb-2 text-blue-600">•	Affichage des descriptions</h3>
        <p>
            Faire les modifications nécessaires pour le champ desc d'un nœud soit affiché, s'il est présent
            Réalisé les tests pour éviter une erreur si le champ n’existe pas
        </p>
        <h3 class="font-medium leading-tight text-xl mt-0 mb-2 text-blue-600">•	TailWindCSS et DaisyUI</h3>
        <p>DaisyUI est une librairie fabriquée à partie de TailWindCSS. Elle permet de réduire la quantité de CSS à écrire pour donner formes stylistiquement aux composants. Ceci en se basant sur des templates et des classes CSS prêt à l’emploi.</p>
    </section>

    <footer class="font-medium leading-tight text-2xl mt-0 mb-0 text-blue-100">
        Bastien KATUSZYNSKI
    </footer>
</main>