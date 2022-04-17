<template>
    <div class="projects">
        <div class="type" v-if="type == 'web'">
            <div v-for="project in webProjects" v-bind:key="project" class="project">
                <h3>{{project.title}}</h3>
                <p>{{project.paragraph}}</p>
                <div class="links">
                    <LinkComp link="{{project.links.demo}}" title="Voir le projet"/>
                    <LinkComp title="Voir le code source"/>
                </div>
            </div>
        </div>
        <div class="type" v-else-if=" type == 'design'">
            <div v-for="project in designProjects" v-bind:key="project" class="project">
                <h3>{{project.title}}</h3>
                <p>{{project.paragraph}}</p>
                <div class="links">
                    <LinkComp link="{{project.links.demo}}" title="Voir le projet"/>
                    <LinkComp title="Voir le code source"/>
                </div>
            </div>
        </div>
    </div>
    
</template>

<script>
import LinkComp from "./LinkComp.vue"

    export default {
        name:"ProjectComp",
        components: {
            LinkComp,
        },props: {
            type: {
                type: String,
                default: "web"
            },
        },
            data() {
        return {
            webProjects: [
                {
                    title: "Tesla",
                    paragraph: "J’ai un intérêt pour l’automobile. Dans ce projet, j’ai intégré une maquette servant de page de présentation des véhicules Tesla. L’animation est faite grâce à GSAP.",
                    links: [{
                        demo: "https://www.perdu.com",
                        sourceCode: "https://www.perdu.com"
                    }]
                },
                {
                    title: "BMW M4",
                    paragraph: "Dans ce projet, j’ai imaginé une page de présentation pour la BMW M4. J’ai voulu particulièrement soigné le chargement. J’ai pu utiliser la librairie GSAP pour l’animation."
                },
                {
                    title: "Mocha Café",
                    paragraph: "Lors de ma recherche de stage de 2ème année, j’ai effectué des tests au sein de l’entreprise Numendo. Je devais reproduire une maquette autour de la thématique du café."
                },
                {
                    title: "Les cartes projets",
                    paragraph: "Lors du développement de mon portfolio, j’ai décidé de créer des cartes projets personnalisés. Voici le résultat ! J’ai également ajouté un effet de mouvement dans la première carte en utilisant la libraire tilt.js."
                },
                {
                    title: "Matrix",
                    paragraph: "À l’occasion de la sortie du dernier film Matrix, j’ai tenté de créer une page qui reprend la direction artistique du 4ème volet de la saga."
                },
                {
                    title: "Calculatrice de matrices",
                    paragraph: "Afin de vérifier mes calculs pour mon module de maths pour le web, j’ai codé une calculatrice de matrices, qui permet d’effectuer un produit matriciel."
                },
                {
                    title: "Fonctions mathématiques",
                    paragraph: "Dans le cadre du module de mathématiques, j’ai été en charge de développer plusieurs fonctions mathématiques. Ce projet de première année permet de calculer le PGCD, le PPCM, les coefficients de Bézout ainsi que la factorisation en nombres premiers pour deux nombres donnés mais également de chiffrer votre message selon le décalage que vous souhaitez."
                },
                {
                    title: "Mercedes-Benz",
                    paragraph: "J’ai décidé de créer une page d’accueil pour le site web de Mercedes-Benz d’après une maquette trouvée sur Dribbble."
                },
                {
                    title: "Ancien portfolio Angular",
                    paragraph: "Accompagné d’un ingénieur études et développement de SFEIR Strasbourg, j’ai pu créer mon portfolio sous Angular en reprenant un thème HTML pré-construit. Le principal objectif de ce projet était de mieux connaître l’environnement Angular."
                },
                {
                    title: "Switch Jour-Nuit",
                    paragraph: "Jouez avec le switch pour découvir ce qu’il déclenche !"
                },
            ],
            designProjects: [
                {
                    title: "Euro 2021",
                    paragraph: "À l’occasion de l’Euro 2021, j’ai produit une affiche pour le match France-Suisse."
                },
                {
                    title: "Whistle",
                    paragraph: "Étant un grand fan de football, j’ai imaginé le logo d’un réseau social pour fans. À long terme, mon projet serait de designer l’interface de cette application et de la développer !"
                },
                {
                    title: "Watermelon Studio",
                    paragraph: "Dans le cadre d’un projet en module d’anglais, nous avons dû créer une agence fictive. Voici l’identité graphique de cette dernière."
                },
                {
                    title: "Maison Alsacienne de Biscuiterie",
                    paragraph: "Dans le cadre d’un projet en module d’anglais, nous avons dû créer l’identité graphique de la Maison Alsacienne de Biscuiterie. Voici l’identité graphique de cette dernière."
                },
                {
                    title: "Carte Gold | Carte Noire",
                    paragraph: "Originaire de la Courneuve, le rappeur Dinos a partagé deux titres avant la sortie de son premier album. Ces deux morceaux, respectivement Carte Gold et Carte Noire, servaient à faire la promotion de ce dernier. J’ai donc imaginé deux vraies cartes bancaires à l’effigie du rappeur."
                },
                {
                    title: "Ultra",
                    paragraph: "Au cours de l’année 2021, le rappeur Booba a sorti son dernier album intitulé « Ultra ». Afin de célébrer la sortie de l’album, j’ai créé une pochette fictive du projet en 3D."
                },
                {
                    title: "Burak « Kral » Yilmaz",
                    paragraph: "Otto. C’est à travers ces quatre lettres que le rappeur SCH nous parle de son père dans ce titre, issu de son album JVLIVS. J’ai décidé de créer une pochette dans ce thème."
                },
                {
                    title: "Otto",
                    paragraph: "Otto. C’est à travers ces quatre lettres que le rappeur SCH nous parle de son père dans le titre éponyme, issu de son album JVLIVS. L’illustration a pour but d’être une pochette pour le morceau."
                },
                {
                    title: "Nouvo Mode",
                    paragraph: "Sorti le 6 mars, l’album Nouvo Mode de Sneazzy était l’un des projets que j’attendais le plus en 2020. Dès son annonce j’ai commencé à travailler sur la pochette que j’allais poster sur les réseaux."
                },
                {
                    title: "Project Resident Evil 2",
                    paragraph: "Propulsé sur Orion, une console fictive, redécouvrez Resident Evil 2, un jeu d'horreur sorti en 1998 et réadapté en 2019. Après avoir eu une très bonne expérience avec la version sortie en 2019, j'ai décidé de créer des modèles 3D des armes de Leon S. Kennedy (l'un des personnages principaux) et d’autres éléments du jeu."
                },
            ]
        }
    },
    }
</script>

<style lang="scss" scoped>

.projects {
    .project {
        h3 {
            font-size: 16px;
            font-weight: 500;
        }
        p {
            font-size: 12px;
            margin-top: 10px;
            margin-bottom: 0;
            color: #6D6D6D;
        }
        .links {
            margin-top: 10px;
        }
    }
}
    @media screen and (min-width:1024px) {
        .projects {

            .project {
                
                h3 {
                    font-size: 24px;
                }
                
                p {
                    font-size: 18px;
                    margin-top: 20px;
                }
                
                .links {
                    margin-top: 20px;
                }
            }

            .project:first-child {
                h3 {
                    margin-top: 0;
                }
            }
        }
    }
</style>