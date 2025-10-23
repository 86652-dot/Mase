# Mase
nupid stigger
import pygame
import random

# Initialize Pygame
pygame.init()

# Screen dimensions
WIDTH, HEIGHT = 400, 600
screen = pygame.display.set_mode((WIDTH, HEIGHT))
pygame.display.set_caption("Flappy Bird - Black Bird")

# Colors
WHITE = (255, 255, 255)
BLACK = (0, 0, 0)
GREEN = (0, 200, 0)
BLUE = (135, 206, 250)

# Clock for controlling frame rate
clock = pygame.time.Clock()
FPS = 60

# Bird properties
bird_x = 50
bird_y = HEIGHT // 2
bird_radius = 15
bird_velocity = 0
gravity = 0.5
jump_strength = -10

# Pipe properties
pipe_width = 70
pipe_gap = 150
pipe_speed = 3
pipes = []

# Font for score
font = pygame.font.SysFont(None, 40)
score = 0

# Function to create new pipes
def create_pipe():
    height = random.randint(100, HEIGHT - 200)
    top_pipe = pygame.Rect(WIDTH, 0, pipe_width, height)
    bottom_pipe = pygame.Rect(WIDTH, height + pipe_gap,
