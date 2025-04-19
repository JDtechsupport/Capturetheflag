# Capturetheflag
game where you have to capture the flag
i want to create a came where you have to capture the flagg
import pygame
import math

# Initialize pygame
pygame.init()

# Set up the display
screen = pygame.display.set_mode((800, 600))
pygame.display.set_caption('Spinning Welcome')

# Define colors
RED = (255, 0, 0)
WHITE = (255, 255, 255)

# Set font
font = pygame.font.SysFont("Arial", 60)

# Load the text surface
text_surface = font.render('Welcome', True, RED)
text_rect = text_surface.get_rect(center=(400, 300))

# Main loop
running = True
angle = 0
while running:
    # Handle events
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Clear the screen
    screen.fill(WHITE)

    # Rotate the text
    rotated_text = pygame.transform.rotate(text_surface, angle)
    new_rect = rotated_text.get_rect(center=text_rect.center)

    # Draw the rotated text
    screen.blit(rotated_text, new_rect)

    # Update the display
    pygame.display.flip()

    # Increase the angle for spinning effect
    angle += 1

    # Control the speed of rotation
    pygame.time.delay(10)

# Quit pygame
pygame.quit()
