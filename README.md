# 3D_Raycasting_Game
Cub3d is a project from the 42 Network curriculum where you create a simple 3D game using raycasting with vectors instead of angles. Inspired by classic games like Wolfenstein 3D, this project involves rendering a 3D environment from a 2D map and implementing basic game mechanics.

### Project: cub3d (42 Network)

**Cub3d** is a project within the 42 Network's curriculum designed to introduce students to the basics of 3D graphics programming. Inspired by early first-person shooter games like Wolfenstein 3D, this project combines elements of computer graphics, mathematics, and game development to create a simple 3D game environment from a 2D map using the raycasting technique. Here’s an overview tailored to the approach where raycasting is implemented using vectors instead of angles.

#### Project Goals:

1. **Graphics Rendering**: To create a pseudo-3D perspective by rendering 2D maps into a 3D-like environment.
2. **Mathematics Application**: To apply geometric transformations and vector mathematics in simulating a 3D world.
3. **Programming Proficiency**: To enhance skills in C programming, particularly in memory management, algorithms, and data structures.
4. **Understanding Game Mechanics**: To learn the basics of player movement, collision detection, and environment interaction.

#### Core Concepts:

1. **Raycasting with Vectors**:
   - **Vector Mathematics**: Instead of using angles to cast rays and determine wall intersections, vectors represent the direction and position of each ray. This allows for a more straightforward computation of the intersection points between rays and map boundaries.
   - **Direction Vectors**: Each ray is represented by a direction vector originating from the player’s position. These vectors are used to compute the distance to the closest wall.
   - **Perpendicular Distance Calculation**: For each ray, the perpendicular distance to the wall is calculated using dot product operations, which helps in determining the correct scaling for the wall slice to be rendered on the screen.

2. **Rendering Engine**:
   - **2D Map to 3D Projection**: A 2D grid map is transformed into a 3D visual representation by shooting rays from the player's position and finding their intersection with walls.
   - **Vertical Strip Rendering**: Each ray corresponds to a vertical strip on the screen, with its height proportional to the distance from the player to the wall. This mimics the effect of perspective in a 3D environment.

3. **Player Movement and Interaction**:
   - **Directional Control**: The player can move forward, backward, and rotate, altering the direction vectors and updating the view accordingly.
   - **Collision Detection**: The engine checks for collisions between the player's bounding box and walls, preventing the player from moving through solid objects.

4. **Optimizations and Enhancements**:
   - **Texture Mapping**: Wall textures can be applied to give a more realistic appearance to the surfaces.
   - **Lighting and Shading**: Basic lighting effects can be implemented to enhance depth perception and realism.

5. **Project Requirements**:
   - **C Language**: The entire project is to be coded in C, adhering to the 42 Network’s coding standards.
   - **No External Libraries**: Aside from the standard libraries and the given graphic libraries, no external libraries (like SDL, OpenGL) are allowed, emphasizing a deep understanding of low-level graphics programming.
   - **Performance and Efficiency**: The code should be optimized to handle rendering efficiently in real-time.

#### Implementation Details:

In your vector-based raycasting approach, here's a breakdown of how you might structure the raycasting:

1. **Initialize Raycasting**:
   - Define the player's position and direction vectors.
   - Set up a plane perpendicular to the player's view direction, determining the field of view.

2. **Casting Rays**:
   - For each vertical slice of the screen, calculate the direction vector of the corresponding ray.
   - Use the direction vector to determine the intersection of the ray with the grid lines of the map.

3. **Intersection Calculation**:
   - Calculate where the ray intersects with the vertical and horizontal lines of the grid using vector operations.
   - Determine which intersection occurs first, indicating the closest wall in that direction.

4. **Distance Calculation**:
   - Use vector math to compute the exact distance to the wall, accounting for the angle of the ray relative to the player's direction vector.
   - Correct for the fish-eye effect by computing the perpendicular distance to the wall.

5. **Rendering**:
   - Compute the height of the wall slice to be rendered based on the distance.
   - Draw the slice on the screen with the appropriate texture, if applied.

6. **Updating View**:
   - As the player moves or rotates, update the direction vectors and recalculate the ray intersections for the new view.

### Conclusion

The **cub3d** project is a rich learning experience in understanding 3D graphics fundamentals, especially through the lens of raycasting with vector mathematics. It challenges students to combine mathematical precision with programming skills to build a functional and interactive 3D game environment from scratch. This approach not only simplifies the implementation but also deepens the understanding of vector operations in computer graphics.
