cmake_minimum_required (VERSION 3.8.2)
project (MineCraftOWC)
add_executable (minecraft 
./Source/Application.cpp
./Source/Camera.cpp
./Source/Context.cpp
./Source/Controller.cpp
./Source/GL/GLFunctions.cpp
./Source/GlobalInfo.cpp
./Source/Item/ItemStack.cpp
./Source/Item/Material.cpp
./Source/Main.cpp
./Source/Maths/Vector2XZ.cpp
./Source/Maths/Ray.cpp
./Source/Maths/NoiseGenerator.cpp
./Source/Maths/Frustum.cpp
./Source/Maths/Matrix.cpp
./Source/Maths/GeneralMaths.cpp
./Source/Model.cpp
./Source/Physics/AABB.cpp
./Source/Player/Player.cpp
./Source/Renderer/RenderMaster.cpp
./Source/Renderer/WaterRenderer.cpp
./Source/Renderer/FloraRenderer.cpp
./Source/Renderer/CubeRenderer.cpp
./Source/Renderer/SFMLRenderer.cpp
./Source/Renderer/QuadRenderer.cpp
./Source/Renderer/ChunkRenderer.cpp
./Source/Shaders/CloudShader.cpp
./Source/Shaders/FloraShader.cpp
./Source/Shaders/ShaderLoader.cpp
./Source/Shaders/WaterShader.cpp
./Source/Shaders/ProcSkyShader.cpp
./Source/Shaders/ChunkShader.cpp
./Source/Shaders/SunShader.cpp
./Source/Shaders/BasicShader.cpp
./Source/Shaders/PostProcessShader.cpp
./Source/Shaders/Shader.cpp
./Source/Sky/ProcSky.cpp
./Source/Sky/Cloud.cpp
./Source/Sky/SkyManager.cpp
./Source/States/PlayingState.cpp
./Source/Texture/CubeTexture.cpp
./Source/Texture/TextureAtlas.cpp
./Source/Texture/BasicTexture.cpp
./Source/Tick/TickManager.cpp
./Source/ToggleKey.cpp
./Source/Util/FileUtil.cpp
./Source/Util/FPSCounter.cpp
./Source/Util/Random.cpp
./Source/World/Generation/Terrain/ClassicOverWorldGenerator.cpp
./Source/World/Generation/Terrain/SuperFlatGenerator.cpp
./Source/World/Generation/Biome/GrasslandBiome.cpp
./Source/World/Generation/Biome/TemperateForestBiome.cpp
./Source/World/Generation/Biome/LightForest.cpp
./Source/World/Generation/Biome/OceanBiome.cpp
./Source/World/Generation/Biome/DesertBiome.cpp
./Source/World/Generation/Biome/Biome.cpp
./Source/World/Generation/Structures/StructureBuilder.cpp
./Source/World/Generation/Structures/TreeGenerator.cpp
./Source/World/Chunk/ChunkMeshBuilder.cpp
./Source/World/Chunk/ChunkManager.cpp
./Source/World/Chunk/Chunk.cpp
./Source/World/Chunk/ChunkMesh.cpp
./Source/World/Chunk/ChunkSection.cpp
./Source/World/Event/PlayerDigEvent.cpp
./Source/World/Block/BlockTypes/BlockType.cpp
./Source/World/Block/ChunkBlock.cpp
./Source/World/Block/BlockData.cpp
./Source/World/Block/BlockDatabase.cpp
./Source/World/World.cpp)
set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake_modules" ${CMAKE_MODULE_PATH})
set_property(TARGET minecraft PROPERTY CXX_STANDARD 17)
set_property(TARGET minecraft PROPERTY CXX_STANDARD_REQUIRED ON)
find_package(SFML 2.4 REQUIRED graphics window system)
find_package(Threads)
find_package(OpenGL)
file(COPY Res Shaders DESTINATION ${CMAKE_BINARY_DIR})
option(SFML_STATIC_LIBRARIES "Set to TRUE to link libraries statically. Requires statically built SFML." FALSE)
target_link_libraries(minecraft Threads::Threads ${OPENGL_gl_LIBRARY} ${SFML_LIBRARIES} ${SFML_DEPENDENCIES} )

