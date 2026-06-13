# VkReflection

**VkReflection** is a lightweight metadata system for Vulkan API structures.

It parses the Khronos-provided `vk.xml` registry and extracts structural metadata that can be queried at runtime. The generated metadata includes:
- Structure names
- Member information
    - Member name
    - Type
    - Memory offset
- Nested structure relations

The library also provides a runtime interface for loading and accessing the generated metadata through an iterable container, making it easier to inspect and traverse Vulkan structures within your application.

**Features**
- Parse Vulkan structure definitions generated from `vk.xml`
- Uses *libcurl* to download the `vk.xm` from a provided source, or provide your own sources list 
- Generate compact binary metadata
- Support full registry or selective metadata generation
- Runtime metadata loading and querying 
- Lightweight and simple integration

**Limitations**
VKReflection is intentionally minimal in scope. It is not a complete Vulkan reflection system and should be vied as a lightweight emtadata layer rather than a full-featured reflection framework.

Its primary goal is to expose basic structural information about Vulkan types in a format that is easy to serialise, load and query at runtime.