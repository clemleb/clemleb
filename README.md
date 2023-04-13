- 👋 Hi, I’m @clemleb
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
clemleb/clemleb is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
# Importer les modules nécessaires pour le diorama
import pygame
from pygame.locals import *

# Initialiser Pygame
pygame.init()

# Définir les dimensions de la fenêtre
largeur_fenetre = 800
hauteur_fenetre = 600

# Créer la fenêtre du diorama
fenetre = pygame.display.set_mode((largeur_fenetre, hauteur_fenetre))

# Charger les images des éléments du diorama
image_fond = pygame.image.load("fond.jpg")
image_superheroine = pygame.image.load("superheroine.png")
image_pluie = pygame.image.load("pluie.png")

# Définir la position initiale de la super-héroïne
position_superheroine_x = 100
position_superheroine_y = 400

# Définir la position initiale de la pluie
position_pluie_x = 0
position_pluie_y = 0

# Boucle principale du diorama
while True:
    # Gérer les événements
    for evenement in pygame.event.get():
        if evenement.type == QUIT:
            pygame.quit()
            sys.exit()

    # Afficher l'image de fond
    fenetre.blit(image_fond, (0, 0))

    # Afficher l'image de la super-héroïne
    fenetre.blit(image_superheroine, (position_superheroine_x, position_superheroine_y))

    # Afficher l'image de la pluie
    fenetre.blit(image_pluie, (position_pluie_x, position_pluie_y))

    # Mettre à jour la position de la pluie
    position_pluie_y += 5

    # Vérifier si la pluie a atteint le bas de l'écran
    if position_pluie_y > hauteur_fenetre:
        # Réinitialiser la position de la pluie
        position_pluie_y = 0

    # Mettre à jour l'affichage de la fenêtre
    pygame.display.flip()
