# resume-cv-curriculum-vitae-responsive-web-component
My resume  : http://buze.michel.chez.com/cv_michel_buze.html

It's RESPONSIVE
It's WYSYWIG (A4 format)
On web display buttons to print and download Word & PDF
Uses web components to avoid duplicade code!

To make PDF : Firefox : Print to PDF; to make Word, open PDF and Export as DOCX...
Here is the code :

<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CV de Michel Buze - Ingénieur Logiciel Bordeaux Développeur Java Fullstack</title>

    <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">	
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400&display=swap" rel="stylesheet">	

    <style>
		@media screen and (min-width: 1600px) {
			body {
				/* webkit browsers */
				zoom: 120%;
				/* moz browsers , since there is no support to "zoom" */
				-moz-transform: scale(1.2);
				-moz-transform-origin: 0 0
				}
		}	
        body {
            font-family: Roboto, Arial, sans-serif;
            margin: 0; /* Suppression des marges par défaut */
            padding: 0px; /* Espacement général autour du corps */
			background:linear-gradient(0deg, #d8d8de, #c2c2cc);
			background:transparent;
        }
        .container {
            max-width: 800px; /* Largeur maximale du conteneur */
            margin: auto; /* Centrage du conteneur */
			background: #ffffff; /* Fond blanc pour le conteneur */
            padding: 2px; /* Espacement à l'intérieur du conteneur */
            border-radius: 10px; /* Arrondir les bords du conteneur */
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); /* Ombre pour donner du relief */
        }
		.hide {
			text-align: center;
		}		
		span.bouton {
			border-radius:3px;
			background-color:#f0f0f0; 
			text-decoration:none;
			display:inline-block;
			transition:transform 0.8s ease-in-out;
			border:1px solid #a0a0a0;
			margin:4px;
			padding:4px;
			color:black;
		}
		span.bouton:hover {
			color:#000080;
			background-color:#fefefe;
			transition:transform 1.0s ease-in-out;
		}
		
		.iprint{ background:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAMAAAAoLQ9TAAAABGdBTUEAAK/INwWK6QAAABl0RVh0U29mdHdhcmUAQWRvYmUgSW1hZ2VSZWFkeXHJZTwAAAGzUExURdfX1/n5+fz8/Lu7u2FhYYGBgWWXyujo6PH1+c3j+2SXye3z+MLc+N/f35eXl+zy92WYym5ubnp6eu70+NPT09LS0oS24s3Nzc/j/EqFx5aWltfn/vj7/XV1ddPn/dLm/N/p9Pb4+qOjo/b3+bvW9by8vI2v3cPd+crh+sjg+s/k/MzMzPD0+fD0+NjY2ISo1UqFxOzy+Gtra3yq18zh+93d3c3m/Onv9aqsr6urq9Xn/aGhofv7++nw+GKWyIeHh46OjrnO6Obt90NDQ+/0+iUlJSQkJMfg+tHk/FGNyHBwcLXU883j/GSXyu/0+Y2NjU2IxUtLS0yJxVWQy9jo/sjg+W1tbcbGxnFxcU6Lx73a9s7OzmGUx5WVlVhYWNTU1Nfm8k+MyMPDw+30+iMjI0JCQuHq9CwsLNfo/j8/P+30+Zubm02JxXl5eZqamnR0dNPm/NPl/fr7/VCMyCoqKqenp+zx+cTd+X2y4kiAw1KNyIODg+vx+WGVx8TExFJSUk+MxlWRymKVyN7o8oSEhH5+fmmV26iqrUiDxLW1tb3Axb+/v7m5ucvLy/Ly8n19ff///wT2/scAAADoSURBVHjaYpgwYYKjcXFiY3CO2gQQYADiAH5hbm7DhIq2IqhAFYcPZyiPjJmYPlTAk0NCS6Ncgd+8EiJg06BTIMepqeKta8AIEoi2D/KTtpI34Yly6WBRncBgmqcdmRWSUejhrp4smZQvzsAnyt4PB+x1YQwtTEy9fVAQzsQUwdDKyGjJ2wsGvEqMjCwMQgwMfHrdYMDgwMCQySDLzOwf3wMGItXMzCUMXp2dsaysuYIs9c6pgp2drgxGpZ2sFl1g0J7emZ3CYC0UV6tcVmPrlNasGOMWKAXyi50AGxubLxeXQBOQAxBgAJdSVWkF8xRLAAAAAElFTkSuQmCC) top left no-repeat;		}
		.idoc{ background:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQBAMAAADt3eJSAAAABGdBTUEAALGPC/xhBQAAACBjSFJNAAB6JgAAgIQAAPoAAACA6AAAdTAAAOpgAAA6mAAAF3CculE8AAAAElBMVEUAAADAwMCAgIAAAP8AgAD///9pN7EFAAAAAXRSTlMAQObYZgAAAAFiS0dEBfhv6ccAAAAHdElNRQffAQ8QKyuMVZrlAAAAV0lEQVQI11WN0QnAIAxEzxFK2wnaBYQ4gAQHKPH2X6WefvkCgTyOHID0OAbpNZHhggzMm+zLeAsUO6zLtJM1ZHJnuWaG5MwYNTK3f8tsf7bPo1vU1T/2DzZMHYItz92LAAAAJXRFWHRkYXRlOmNyZWF0ZQAyMDE1LTAxLTE1VDE2OjQzOjQ0KzAxOjAwtVCFpAAAACV0RVh0ZGF0ZTptb2RpZnkAMjAxNS0wMS0xNVQxNjo0Mzo0MyswMTowMAGqA5YAAAAASUVORK5CYII=) top left no-repeat;		}
		.ipdf{ background:url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAAABHNCSVQICAgIfAhkiAAAAAlwSFlzAAALEgAACxIB0t1+/AAAABV0RVh0Q3JlYXRpb24gVGltZQA5LzExLzA24EiMeQAAABx0RVh0U29mdHdhcmUAQWRvYmUgRmlyZXdvcmtzIENTNXG14zYAAAIsSURBVDiNhZNdSJNRGMd/5/iStq8ww9aqaUVDwXRdZDdNN7AY9AHddRF4EQlR1F0UIUUsLIQgzIvCuxCSQLrICII+1HBSUNCXmlnkYppZrmLj3cd7usjNvTn0gQMHzv//e57zPOcI8qKrul5Z16+jUAgBSUPR2Hr6U4V/VzWgA2j5IvfBvdScOIphGHlGgRACKSXRaBS317vp4+P+kS2BhipAF8OeemWVRQWzZkNXBs5HvYyNjeH3+wEYfzLweWugoUqbSaeYIbUkAGBNOk0mk1modueOyu6Wkw+1n5nlzQCGYWCz2QiFQkQiETweD/Yi6dO+JnXmloFYZBENUuJyuQgGg8TjcWw2GxPTd9Ha4t/cwEqA9sNHRr3Nh0xm9fIVHDtO5loHpa3ncDgcucZOlVjQgO/MT8NhseJ0Ok2AZOlq5hTIsrKcMTsVJUCLxWKJrLikuBi73W4CiD1NTCuJ9cB+pJQmiEIgTY2aJ+ev38/C/EIy2/dg0ZkhhPkhKf4BctmF4O2ZVjZeucRI5w2ig2EcddtQAsobfahFAGEGjHbeZPL1e/5092Cpq0VWuHlzq4fYl0nW9odZ0RQwj+vO+csqkUioueiUuu0LquurNqjI8Aul67rSdV0lk0mVSqXU7PiESqfTqvdiuypYQV/LKT4MDLGvq4Py7bUIIXJXEkJQurkypy/Yg91X2/BdOIurrsZkzO5zTVf//cbn/YP8ILUgunefpeLd0yH+Aij2yNj1Y8bAAAAAAElFTkSuQmCC) top left no-repeat;		}		
    </style>
	
	<style media="print">
		.hide {
			display: none
		}
        body {
            font-family: Roboto, Arial, sans-serif;
            margin: 0; /* Suppression des marges par défaut */
            padding: 0px; /* Espacement général autour du corps */
			background:transparent;
        }		
	</style>	
</head>
<body>
    <div class="container">
        <header- prenom="MICHEL" nom="BUZE" metier="INGÉNIEUR LOGICIEL" experience="25" 
		         mail="michel.buze@gmail.com" tel="06&nbsp;25&nbsp;88&nbsp;81&nbsp;09" adr="7 rue René Coty" cp="33140" ville="Villenave d'Ornon" >
		</header->

        <section- name="EXPÉRIENCE PROFESSIONNELLE" icon="work">		
                <job- name="Ingénieur Logiciel" debut="(2020" fin="-Présent)" duree=" (4 ans)" societe="Randstad Digital (ESN Informatique)"><br>
					<!--(retraite complémentaire)-->
                    <mission- name="Conception et développement Java" details=": Gestion des actifs." debut="(2022" fin="-Présent)" duree=" (2 ans)" societe="Agirc-Arrco (retraite complémentaire)."><br>
                        <technos- t="Tech lead Java EE, Scrum master, Eclipse, Spring/Spring Batch, Hibernate, Postgres, Vaadin, Webservices, Junit/Mockito, Jenkins, Sonar, Jira/Confluence, Svn/Git."></technos->
                    </mission->
                    <mission- name="Conception et développement Java" details=": Serveur Vocal Interactif (SVI)." debut="(2020" fin="-2022)" duree=" (2 ans)" societe="Orange (OBS)"><br>
                        <technos- t="Linux Ubuntu / VM Windows 10, Java EE (Spring Boot, Hibernate), Maven, IntelliJ, Git, MySQL/MariaDB, Apache Tomcat, Webservices Rest, 
						                   HTML/CSS, Javascript (Node.js, Angular, jQuery (plugin datatables)), Outils de test (Karma (JS), Selenium (IHM), Junit, FitNesse (tests fonctionnels)), Jenkins, Sonar, Jira/Confluence. Scrum (agile).">
						</technos->
                    </mission->
                </job->
				
                <job- name="Ingénieur Logiciel" debut="(2001" fin="-2019)" duree=" (18 ans)" societe="Sogeti High Tech (ESN Hautes Technologies)">
                    <mission- name="Développement / maintenance" details=": Système d’information" debut="(2015" fin="-2020)" duree=" (5 ans)" societe="Ariane Group"><br>
					<!-- applications de gestion et tests de validation fonctionnelle-->
                        <technos- t="Java web (JSP, Struts, Apache Tomcat, webservices Rest/Soap/CXF), C#, JIRA, VBA, Access."></technos->
                    </mission->
					 
                    <mission- name="Conception et développement Java" details=": Simulateur de système drones." debut="(2013" fin="-2024)" duree=" (1 an)" societe="Conseil regional"><br>
                        <technos- t="Android SDK, Java 3D (jMonkey), API Google Earth, SVN, C++."></technos->
					</mission->
		
					<!--Conception et développement, TU/TI-->
                    <mission- name="Développement TestStand/C++" details=": Contrôle électrique d'un lanceur d'engins." debut="(2010" fin="-2012)" duree=" (2 ans)" societe="EADS">
                        <!--<technos- t="TestStand. C++"></technos->-->
					</mission->
					
                    <mission- name="Tests unitaires et d'intégration" details=": Logiciels embarqués." debut="(2005" fin="-2009)" duree=" (4 ans)" societe="(Secteur industriel : Dassault, Turboméca, Sodern, Messier-Bugatti, Alstom; médical : Airox, …)">
					<!--Gestion de Faits Techniques-->
						<!--Langages C et ADA-->
                        <technos- t="RTRT (IBM Rational Test RealTime). C, Ada. Bugzilla, Mantis"></technos->
					</mission->					
 
                    <mission- name="Conception objet/développement" details=": Système de visiocommunication par satellite." debut="(2004" fin="-2005)" duree=" (1 an)" societe="Thales"><br>
                        <technos- t="Unix Temps Réel, Langage C."></technos->
                    </mission->
					
                    <mission- name="Responsable outils" details=": Gestion de configuration/test/compilation. Cockpit avion." debut="(2001" fin="-2003)" duree=" (2 ans)" societe="Thales Avionics"><br>
                        <technos- t="C, Ada, Unix, Rational ClearCase/ClearQuest"></technos->
                    </mission->
                </job->
				
                <job- name="Ingénieur Logiciel" debut="(1997" fin="-2001)" societe="Sopra (ESN Informatique de Gestion)" duree=" (5 ans)">
                    <mission- name="Conception et développement" details=": Facturation client." debut="(2000" fin="-2001)" duree=" (1 an)" societe="France Télécom">
						<!--SGBDR  Oracle et Sybase-->					
                        <technos- t="Oracle, Sybase. C. PL/SQL."></technos->
                    </mission->
                    <mission- name="Analyse et développement / maintenance" details=": Domaine Financier (comptabilité client, crédits à la consommation, échanges interbancaires)." debut="" fin="" duree="" societe="CAMIF (Vente par correspondance).">
                        <technos- t="L4G PowerHouse. Pascal. HP3000"></technos->										
                    </mission->
                </job->	
        </section->

		<!--business_center assignment-->
        <section- name="STAGES" icon="business_center">
                <job- name="Analyste / Développeur" societe="Thales Avionics" debut="(stage de DESS) (1995" fin="-1995)"  duree=" (5 mois)">
                    <mission- name="Analyse et réalisation" details=" d'un outil de tests de non-régression. Logiciel embarqué (cockpit)." debut="" fin="" duree="" societe="">
                        <technos- t="UNIX, C et ADA."></technos->
                    </mission->
                </job->
				
                <job- name="Analyste / Développeur" debut="(1991" fin="-1994)" societe="Diverses ESN (Sylis, UIE, CSIO)" duree=" (3 ans)">
                    <mission- name="Analyse et conception/réalisation d'applications de gestion)" societe="" debut="" fin="" duree=""
					    details=": Système d’information (activité commerciale, R.H., prévision du CA), gestion du patrimoine et de calcul d'impôt, gestion de CV, suivi d'assistance"><br>
                        <technos- t="Borland Paradox, Windev (PC-Soft), SGBDR Access (Microsoft), dBase, Méthode MERISE."></technos->
                    </mission->
                </job->
				
                <job- name="Développeur" debut="(1992" fin="-1992)" societe="Cocktel Vision" duree=" (6 mois)">
                    <mission- name="Programmation du logiciel multimédia éducatif" societe="" debut="" fin="" duree="" details="ADIBOU.">
                        <technos- t="Langage interne, entre Visual Basic et Java."></technos->
                    </mission->
                </job->
        </section->

        <section- name="FORMATION" icon="school">		
                <job- name="DESS de Génie Logiciel" debut="(1994" fin="-1995)" societe="Université Bordeaux I" duree=" (Bac+5)">
                </job->

                <job- name="Formations internes" debut="(1995" fin="-Présent)" societe="Sopra/Sogeti/Randstad Digital" duree=" (3 mois)"><br>
                    <skills- sep="" type="" details="Gestion de projets. Conduite de réunions. Gestion de configuration (ClearCase). Nouvelles technos : web / client/serveur. Objet (conception, UML, UP (process unifié), middleware Corba). Méthodes. SAP. Spring batch. Angular.">
                    </skills->				
                </job->
        </section->

        <section- name="COMPÉTENCES" icon="settings">
			<div style="border: 1px solid #ccc; border-radius: 10px; padding:4px;background-color:white;margin-left: 8px; margin-right: 8px;"> 
				<skills- sep=" : " type="Langages" details="Java, C#, C++/C, Ada, visual Basic, JavaScript, HTML, XML, Pascal, python, shell, awk, lex/yacc."></skills-><br>
				<skills- sep=" : " type="OS" details="Windows, Linux/Unix, Android."></skills->
				<skills- sep=" : " type="SGBD" details="Oracle, MySQL, MariaDB, Postgre, Sybase, Access, SQL."></skills-><br>
				<skills- sep=" : " type="Méthodes" details="UML, Merise, Agiles (Scrum)."></skills-><br>
				<!--IntelliJ, Visual Studio, Jenkins, Sonar, Confluence, etc.-->
				<skills- sep=" : " type="Outils" details="Gestion de configuration (Git, ClearCase, SVN), Gestion de faits techniques (Jira, ClearQuest, Bugzilla, Mantis, …), 
														  Outils de tests (RTRT, TestStand), Eclipse, Rational Rose, PLM Windchill, Wiki, Bureautique."></skills->
				
				
			</div>
        </section->

        <section- name="DIVERS" icon="category">
			<div style="border: 1px solid #ccc; border-radius: 10px; padding:4px;background-color:white;margin-left: 8px; margin-right: 8px;"> 
				<skills- sep=" : " type="État civil" details="53 ans. Célibataire. Né le 24/06/1971 à Valence (Espagne). Nationalité française"></skills-><br>
				<skills- sep=" : " type="Langues" details="ANGLAIS	(courant (anglais technique), séjour de 3 semaines aux USA), ESPAGNOL (bilingue)."></skills-><br>
				<skills- sep=" : " type="Autres" details="PERMIS voiture. Rédacteur sur Wikipédia et un webmedia (WordPress). Webmaster d'un site personnel."></skills->
			</div>
        </section->
    </div>

<!-- @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
     @@@@@@@@@@@@@@@@@@@@@@@      BOUTONS                          @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
	 @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@ -->

<div class="hide">
	<!--<center>-->
	<br>
		
<a href="http://buze.michel.chez.com/cv_michel_buze.html" onclick="javascript:window.print();return false;">
<span class="bouton">			<span class="iprint">&nbsp;&nbsp;&nbsp; </span>&nbsp;
							Imprimer le CV </span></a>
			
<a target="doc" href="http://buze.michel.chez.com/cv_michel_buze.docx" title="">							
<span class="bouton">			<span class="idoc">&nbsp;&nbsp;&nbsp;&nbsp; </span>	
							Télécharger (.docx <span class="d2">:</span> Microsoft Word)</span></a>
			
<a target="pdf" href="http://buze.michel.chez.com/cv_michel_buze.pdf" title="">							
<span class="bouton">			<span class="ipdf">&nbsp;&nbsp;&nbsp;&nbsp; </span>
							Télécharger (.pdf <span class="d2">:</span> Adobe Acrobat)</span></a>		
	
	<!--</center>-->
</div>

    <script>
        class HeaderComponent extends HTMLElement {
            constructor() {
                super();
                const shadow = this.attachShadow({ mode: 'open' });

                const mail = this.getAttribute('mail');
                const tel = this.getAttribute('tel');

                const wrapper = document.createElement('div');
                wrapper.innerHTML = `
                    <style>
						.icon {
							font-family:'Material Icons';
							vertical-align: middle; /* Pour centrer verticalement les icônes */
							margin-right:2px;
							color:#666666;
							font-size:16px;
						}							
						.header-line1 {
							box-shadow: 0 0 10px rgba(0, 0, 0, 0.9); /* Ombre pour donner du relief */
							font-size: 1.45em;
							text-align:center;
							border-radius:40px;
							background:linear-gradient(0deg, #f8f8ff, #e0e0ee);
						}
						.header-line2, a {
							color: #404040;
							font-size: 1em;	
							text-decoration: none; 
						}						
                        .header-line1, .header-line2 {
                            margin: 0px 0px 0px 0px; /* Marges réduites pour impression */
                        }
                    </style>
					<style media="print">
						.icon {
							display: none
						}
					</style>					
					
                    <div class="header-line1">
						${this.getAttribute('prenom')} ${this.getAttribute('nom')}. 
						${this.getAttribute('metier')}. <span style="font-size:16px">${this.getAttribute('experience')} ans d'expérience.</span>
					</div>
					
					<div class="header-line2">
					<div class="header-line2">
							&nbsp;
                            <span><span class="material-icons icon"">mail</span><a href="mailto:${mail}">${mail}</a></span> <font color=#aaaaaa>/</font>
                            <span><span class="material-icons icon"">phone</span><a href="tel:${tel}">${tel}</a></span> <font color=#aaaaaa>/</font>
                            <span><span class="material-icons icon">home</span>${this.getAttribute('adr')}. ${this.getAttribute('cp')} ${this.getAttribute('ville')}</span>
							
					<!--
					<div style="font-size:12px">
					Ingénieur logiciel avec plus de 25 ans d'expérience (Randstad Digital, Sogeti HT, Sopra, ...) en conception, développement et tests d'applications pour divers secteurs (aéronautique, télécoms, tertiaire).
					Maîtrise Java, C#, C++, le développement web, les bases de données ainsi que le code embarqué.					
					</div>
					-->
                    </div>
                `;
                shadow.appendChild(wrapper);
            }
        }

        class MissionComponent extends HTMLElement {
            constructor() {
                super();
                const shadow = this.attachShadow({ mode: 'open' });

                const wrapper = document.createElement('div');

                const duree = this.getAttribute('duree') || "";
                const societe = this.getAttribute('societe') || "";
				
                wrapper.innerHTML = `
                    <style>
                        .mission {
							font-size:0.93em;
                            margin-left: 1px; /* Recul pour les missions */
                            line-height: 1.1; /* Hauteur de ligne réduite */
                            padding: 2px; /* Espacement à l'intérieur de la mission */
                            margin-bottom: -4px; /* Réduction de l'espace en bas des missions */
							border-top: 1px solid #d4d4d4; /* Ligne fine claire en dessous */
							padding-bottom: -3x; /* Ajout d'espacement en bas pour la ligne */							
							padding-top: 3px;
                        }
                        .dates {
                            font-weight: normal; 
							color:#404040;
							font-size:0.85em;
                        }
                        .soc {
							font-size:0.85em;
							color:#202020;
                        }						
                    </style>
                    <div class="mission">
                        <strong>${this.getAttribute('name')}</strong> <span style="font-size:15px">${this.getAttribute('details')}</span>
						<span class=soc>${societe}</span> <span class="dates">${this.getAttribute('debut')}${this.getAttribute('fin')}${duree}</span>
                        <slot></slot>
                    </div>
                `;
                shadow.appendChild(wrapper);
            }
        }

        class JobComponent extends HTMLElement {
            constructor() {
                super();
                const shadow = this.attachShadow({ mode: 'open' });

                const wrapper = document.createElement('div');
                const duree = this.getAttribute('duree') || "";
                const societe = this.getAttribute('societe') || "";

                wrapper.innerHTML = `
                    <style>
                        .job-details {
							margin-top:0px;
                            margin-left: 8px; 
							margin-right: 8px; 
                            line-height: 1.0; 
                            border: 1px solid #ccc; 
                            border-radius: 10px; 
                            padding: 4px; 
                            margin-bottom: 4px; 
							background-color: white; /* Fond blanc pour la section */
						}
                        .job-title {
                            font-weight: bold; 
							color:#000060;
							font-size:17px;
                        }
                        .dates {
                            font-weight: normal; 
							color:#404040;
							font-size:0.85em;
                        }
                        .soc {
							font-size:16px;
							color:#302080;
                        }						
                    </style>
                    <div class="job-details">
                        <span class="job-title">${this.getAttribute('name')}</span>. <span class=soc>${societe}</span> <span class="dates">${this.getAttribute('debut')}${this.getAttribute('fin')}${duree}</span>
                        <slot></slot>
                    </div>
                `;
                shadow.appendChild(wrapper);
            }
        }

        class SectionComponent extends HTMLElement {
            constructor() {
                super();
                const shadow = this.attachShadow({ mode: 'open' });

                const wrapper = document.createElement('div');
                wrapper.innerHTML = `
                    <style>		
						.icon {
							font-family:'Material Icons';
							vertical-align: top; /* Pour centrer verticalement les icônes */
							margin-right:-2px;
							color:#444444;
							font-size:16px;
						}		
                        .section {
                            border-radius: 10px; /* Coins arrondis */
							background-color: #f4f4fa; /* Fond blanc pour la section */
                            padding: 0px; /* Espacement à l'intérieur de la section */
                            box-shadow: 0 0 5px rgba(0, 0, 0, 0.1); /* Ombre légère pour le relief */
                        }
                        .section-name {
                            font-weight: bold; /* Titre de la section en gras */
							letter-spacing:2px;
                            font-size: 17px; /* Taille de police pour le titre de la section */
                            padding: 2px; /* Espacement à l'intérieur du titre */
							background:linear-gradient(0deg, #f0f0ff, #ccccdd);
                            border-radius: 40px; /* Coins arrondis pour le titre */
                        }
                    </style>
					
					<style media="print">
						.icon {
							display: none
						}
					</style>					
					
                    <div class="section">
                        <div class="section-name">
						&nbsp;<span class="material-icons icon"">${this.getAttribute('icon')}</span>
						${this.getAttribute('name')}
						</div>
                        <slot></slot>
                    </div>
                `;
                shadow.appendChild(wrapper);
            }
        }

        class SkillsComponent extends HTMLElement {
            constructor() {
                super();
                const shadow = this.attachShadow({ mode: 'open' });

                const wrapper = document.createElement('span');
                wrapper.innerHTML = `
                    <style>
                        .skill {
                            font-size: 15px; /* Taille de police */
                            line-height: 1.2; /* Hauteur de ligne */
							zpadding-left: 8px; /* Espacement à l'intérieur du skill */												
							background-color: white; /* Fond blanc pour la section */							
                        }
                        .skill-type {
						    font-size: 15px; /* Taille de police */
                            font-weight: bold; /* Type en gras */
                        }
                    </style>
                    <span class="skill"><span class="skill-type">${this.getAttribute('type')}</span>${this.getAttribute('sep')} ${this.getAttribute('details')}</span>
                `;
                shadow.appendChild(wrapper);
            }
        }

        class TechnosComponent extends HTMLElement {
            constructor() {
                super();
                const shadow = this.attachShadow({ mode: 'open' });

                const wrapper = document.createElement('span');
                wrapper.innerHTML = `
                    <style>
                        .technos {
                            font-size: 15px; /* Taille de police pour les technos */
							color: #602060;
                        }
                    </style>
                    <span class="technos">${this.getAttribute('t')}</span>
                `;
                shadow.appendChild(wrapper);
            }
        }

        customElements.define('header-', HeaderComponent);
        customElements.define('mission-', MissionComponent);
        customElements.define('job-', JobComponent);
        customElements.define('section-', SectionComponent);
        customElements.define('skills-', SkillsComponent);
        customElements.define('technos-', TechnosComponent);
    </script>
</body>
</html>
