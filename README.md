# Niagara

This is a Vulkan renderer that is written on stream from scratch - without using any third party code that is Vulkan specific. We are using non-Vulkan-specific third party libraries however.

The goal is to experiment with a few modern Vulkan rendering techniques, such as GPU culling & scene submission, cone culling, automatic occlusion culling, task/mesh shading, and whatever else it is that we will want to experiment with.
The code will be written exclusively on stream.

# Requirements

The renderer is written using Visual Studio and targets Windows desktops with modern Vulkan drivers. You will need Visual Studio 2017 and Vulkan SDK to follow along

# Stream

The development of this project streams on YouTube on weekends; Saturday and Sunday, 10 AM PST. You can watch the stream here: https://www.youtube.com/c/zeuxcg/live

Playlist: https://www.youtube.com/playlist?list=PL0JVLUVCkk-l7CWCn3-cdftR0oajugYvd

1. Setting up instance/device and filling the screen with a solid color: https://youtu.be/BR2my8OE1Sc
2. Rendering a triangle on screen: https://youtu.be/5eS3gsL_P-c
3. Cleaning up validation errors and implementing swapchain resize: https://youtu.be/_VU-G5rglnA
4. Rendering a mesh using shader storage buffers and int8: https://youtu.be/nKCzD5iK71M

# Issues

During the streams we find various bugs in parts of the Vulkan stack and report them:

* vkAcquireNextImageKHR crashes in validation layers if vkGetSwapchainImagesKHR hasn't been called \
https://github.com/KhronosGroup/Vulkan-ValidationLayers/issues/358

* vkGetPhysicalDeviceSurfaceFormatsKHR doesn't fill format count correctly \
https://software.intel.com/en-us/forums/graphics-driver-bug-reporting/topic/797666

* Fix NonWritable check when vertexPipelineStoresAndAtomics not enabled \
https://github.com/KhronosGroup/Vulkan-ValidationLayers/issues/73

* Implicit int8->float cast adds Int8 capability to the shader without asking for GL_KHX_shader_explicit_arithmetic_types \
https://github.com/KhronosGroup/glslang/issues/1525
