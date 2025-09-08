# art_tech_playground.py
# A creative journey: coding experiments + pixel-perfect designs + playful playful prototypes

import pygame
import random
import math 

# Initialize Pygame
pygame.init()
WIDTH, HEIGHT = 800, 600
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Art + Tech Playground 🎨💻")

# Clock for controlling frame rate
clock = pygame.time.Clock()

# Main lop  
running = True
angle = 0

while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    # Fill background
    screen.fill((10, 10, 30))

    # Draw colorful moving circles
    for i in range(50):
        x = WIDTH // 2 + int(math.cos(angle + i) * (100 + i * 3))
        y = HEIGHT // 2 + int(math.sin(angle + i) * (100 + i * 3))
        color = (random.randint(100, 255), random.randint(50, 255), random.randint(50, 255))
        pygame.draw.circle(screen, color, (x, y), 8)

    # Update the display
    pygame.display.flip()

    # Increment angle for animation
    angle += 0.02
    clock.tick(60)

pygame.quit()
