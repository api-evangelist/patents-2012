---

title: Point sprite rendering in a cross platform environment
abstract: Method, system, and computer-readable medium for emulating a point sprite represented by a three dimensional vertex in a cross platform environment. The system includes a three dimensional vertex representing a point sprite and a vertex and fragment shaders written in the first programming language. One or more variables are assigned to a set of points representing the 3D vertex using the vertex shader and convey information from the vertex shader to the fragment shader. The point sprite emulator translates the vertex and fragment shaders from the first programming language into a second programming language. The translation includes a transfer of each variable from the vertex shader to the fragment shader such that the information included in each variable is preserved. The point sprite is rendered from the 3D vertex using the translated vertex fragment shaders and displayed on a display screen.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08854368&OS=08854368&RS=08854368
owner: Google Inc.
number: 08854368
owner_city: Mountain View
owner_country: US
publication_date: 20120315
---
Point sprites allow real time computer graphics to create an on screen display of realistic smoke flames dust water and other artistic visual effects. Point sprites are generated from a set of three dimensional 3D points that are submitted to a graphics card. The on screen size of the pixels included in each 3D point is adjusted individually to provide an illusion that more geometry than a single point is being drawn. The 3D point is drawn as an axis aligned square with a specific edge length.

The OpenGL application programming interface API and Direct3D D3D API from Microsoft of Redmond Wash. include mechanisms for drawing real time computer graphics that include point sprites on a display screen. However with the ever increasing demand for display of real time computer graphics in a web browser the computer graphics may be provided to the computing device in the OpenGL API when the graphics card in the computing environment that processes real time graphics uses the D3D API or vice versa. As a result cross platform emulation of the real time graphics commands between the OpenGL API and D3D API is essential for the user to experience the desired computer graphics effects. However conventional systems are not designed for cross platform point sprite emulation of point sprites having a size greater than one.

Embodiments include a methods systems and computer readable media for rendering a point sprite represented by a three dimensional 3D vertex in a cross platform environment. The system includes a three dimensional vertex representing a point sprite and a vertex and fragment shaders written in the first programming language. One or more variables are assigned to a set of points representing the 3D vertex using the vertex shader and convey information from the vertex shader to the fragment shader. The point sprite emulator translates the vertex and fragment shaders from the first programming language into a second programming language. The translation includes a transfer of each variable from the vertex shader to the fragment shader such that the information included in each variable is preserved. The point sprite is rendered from the 3D vertex using the translated vertex fragment shaders and displayed on a display screen.

Further features and advantages of the present invention as well as the structure and operation of various embodiments thereof are described in detail below with reference to the accompanying drawings. It is noted that the invention is not limited to the specific embodiments described herein. Such embodiments are presented herein for illustrative purposes only. Additional embodiments will be apparent to persons skilled in the relevant art s based on the teachings contained herein.

While the present invention is described herein with references to illustrative embodiments for particular applications it should be understood that the invention is not limited thereto. Those skilled in the art with access to the teachings herein will recognize additional modifications applications and embodiments within the scope thereof and additional fields in which the invention would be of significant utility.

The system includes a vertex shader and a fragment shader written in the OpenGL ES Shading Language ESSL . The point sprite emulator translates the vertex shader and the fragment shader into the D3D High Level Shader Language HLSL . The translation includes a transfer of each ESSL variable from the vertex shader to the fragment shader using one or more color units. The translation also includes a correction for the difference between the coordinate system associated with Open GL and D3D application programming interfaces APIs . The translation also includes a synthesis of a fragment coordinate variable and translation of a point size variable. The translated vertex and fragment shaders are processed by a GPU and generate the point sprite on a display screen.

Network may be any network or combination of networks that can carry data communication. Such a network may include but is not limited to a local area network medium area network and or wide area network such as the Internet. Network can support protocols and technologies including but not limited to World Wide Web protocols and or services. Intermediate web servers gateways or other servers may be provided between components of the system shown in depending upon a particular application or environment.

Web server is an electronic device capable of sending receiving and storing resources . Resources are any data that can be provided over network . Resources include data inserted into hypertext markup language HTML pages word processing documents portable document format PDF documents two and three dimensional images video feed sources and multimedia content to name only a few. In an embodiment web server receives a request such as an HTTP request from client and in response sends resources for display on client .

Web server hosts multiple websites . Website has one or more webpages associated with a domain name and hosted by one or more web servers . An example website is a collection of webpages formatted in a HTML that can contain resources described herein as well as various programming elements such as scripts.

Client is an electronic computing device capable of requesting receiving and displaying resources over network . Example clients are personal computers mobile communication devices e.g. smartphones tablet computing devices notebooks set top boxes game console embedded systems and other devices that can send and receive resources over network . Client includes a browser a shared system memory a GPU processing module a graphics card that includes a GPU and a processor .

Browser is an application that client executes to display resources to a user. In an embodiment browser may be a multithreaded browser.

Browser includes a rendering module . Rendering module initiates the rendering process for the real time visual content received by browser . Rendering module retrieves resources from browser and passes those resources to a GPU processing module for rendering. For example rendering module splits resources into rendering data and rendering instructions. Rendering data includes the images or video that is displayed on the display screen. Rendering instructions manipulate the rendering data as it being displayed.

Rendering instructions may be written in a platform independent graphics language that a GPU processing module understands and then be converted in to a graphics language that is compatible with the graphics card. For example the platform independent graphics language may be a serialized version of OpenGL for embedded systems such as OpenGL ES 2.0 API OpenGL ES API . A person skilled in the art will appreciate that the OpenGL ES API is a graphics language designed for embedded devices such as mobile phones and video game consoles.

Shared system memory is a memory region on client that is accessible to rendering module and GPU processing module . A person skilled in the art will appreciate that browser may execute in a sandboxed environment because the sandboxed environment limits the access to client s private memory space by malicious software that may be downloaded through network . As a result browser has a limited access to private memory space on client . Shared system memory is a memory space designed for a browser to pass rendering data and rendering instructions for real time graphics processing to GPU .

When rendering module stores rendering instructions and rendering data in shared system memory GPU processing module retrieves those instructions and data for rendering on GPU .

Validation module prevents invalid rendering instructions and rendering data from reaching GPU . For example when rendering module is compromised and begins to issue incorrect rendering instructions validation module prevents those rendering instructions from being executed on GPU . Similarly when rendering module issues rendering data that includes undefined data corrupt data or corrupt rendering instructions validation module prevents those instructions and data from reaching GPU .

Command translation module translates rendering instructions that are in a platform independent graphics language into a graphics language that is specific to the computing platform. For example the Mac OS X or Linux computing platform may use the OpenGL ES API whereas Microsoft s Windows may use the D3D API.

Command translation module includes an OpenGL to D3D Emulator also referred to as Emulator . Emulator translates rendering instructions received in the platform independent graphics language such as OpenGL ES to D3D for a display on a graphics card that understands D3D rendering instructions. Conventional OpenGL to D3D emulators do not support rendering point sprites of greater than size one.

Emulator includes a point sprite emulator . Point sprite emulator supports rendering point sprites of greater than size one when these sprites are specified using the OpenGL API and rendered using the D3D API. is a block diagram of an exemplary point sprite emulator . A three dimensional 3D point set includes a set of vertices. Each vertex in three dimensional 3D point set includes an x y and z coordinate. These vertices may be drawn as quads or other polygons on a display screen. A person skilled in the art will appreciate that a graphics card draws quads and other polygons as multiple triangles on a display screen. The vertices in three dimensional point set may also be rendered as point sprites in which case each vertex is displayed as an individual point sprite on the display screen.

Vertex shader and a fragment shader are computer software programs that may execute on client that are used by a graphics card to manipulate and calculate rendering effects. When vertex shader and fragment shader are written in for example the ESSL point sprite emulator converts the vertex shader and fragment shader into a vertex shader and a fragment shader in D3D s HLSL.

A graphics card uses vertex shader to calculate position color and texture of the objects in the 3D graphics environment and to add special effects. Vertex shader is applied to each vertex in 3D point set by GPU and transforms each vertex from a 3D point into a two dimensional 2D point which appears on a display screen.

A graphics card uses fragment shader to compute color and other attributes of each pixel included in a quad or other polygon that is submitted to a display screen by vertex shader . Some attributes include applying lighting shadows highlights translucency effects etc.

A developer may transmit information from vertex shader to fragment shader using varying variables. When drawing triangles GPU applies vertex shader to each of the three vertices that make up a triangle and a varying variable may be assigned to each vertex. GPU then interpolates each varying variable using fragment shader at each pixel covered by the triangle. When drawing point sprites GPU applies the vertex shader to a single vertex within a 3D point set . GPU handles varying variables differently for point sprites depending on whether the OpenGL API or the D3D API are used. In the OpenGL API the varying variable is supposed to remain constant across the surface of the point sprite.

Conventional systems which translate ESSL into HLSL transmit the varying variables from the vertex shader to the fragment shader using the texture coordinates of the various texture units such as TEXCOORD n where n is the number of the texture unit. However in the D3D API the texture coordinates are specified as being interpolated across the surface of the point sprite between the two dimensional coordinates 0 0 and 1 1 . As a result in the HLSL fragment shader the developer s varying variables are overwritten by the incorrect interpolated values.

In the D3D API the color units COLOR n where n is the number of the color units are interpolated across the surface of triangles but are constant across the surface of point sprites.

Point sprite emulator allows the display of point sprites with a size greater than one in a cross platform environment. For example point sprite emulator translates vertex shader and fragment shader written in ESSL into vertex shader and fragment shader written in HLSL as described herein that allows the vertex shader and fragment shader to display point sprites of different sizes.

Point sprite emulator enables rendering of point sprites on a graphics card compatible with the D3D API by enabling the D3DRS POINTSPRITEENABLE render state.

After point sprite emulator enables the render state point sprite emulator translates the vertex shader into vertex shader and fragment shader into fragment shader so that the varying variables are not corrupted. For example when varying variables exist in vertex shader point sprite emulator transmits varying variables from vertex shader to fragment shader using color units such as COLOR n instead of the texture units as described herein.

After the varying variables are transferred point sprite emulator synthesizes a gl PointCoord variable in fragment shader A person skilled in the art will appreciate that gl PointCoord queries a fragment s position within a point sprite. The point sprite emulator synthesizes gl PointCoord from the zeroth texture unit s texture coordinate such as TEXCOORD 0 .

Point sprite emulator also accounts for differences in the coordinate systems of the OpenGL and D3D APIs. In the OpenGL API a point sprite is rendered as a quad whose upper left corner has s t texture coordinates of 0 0 and whose lower right corner has texture coordinates of 1 1 as illustrated in .

In P is the center of the point sprite and O is the origin 0 0 of the window coordinate system on a display screen. Also the y window coordinate increases from bottom to top but the t texture coordinate of point sprites increases from top to bottom.

In the D3D API a point sprite is also rendered as a quad whose upper left corner has an s t texture coordinate of 0 0 and whose lower right corner has a texture coordinate of 1 1 as illustrated in .

In P is the center of the point sprite and O is the origin 0 0 of the window coordinate system on a display screen. Also the y window coordinate and the t texture coordinate of a point sprite both increase from top to bottom.

As described herein the OpenGL API coordinate system begins in the lower left hand corner whereas the D3D API coordinate system begins in the upper left hand corner. Point sprite emulator thus flips the vertical texture coordinate in order to account for the differences between the OpenGL and D3D coordinate systems. For example the gl PointCoord variable referenced in fragment shader is synthesized from TEXCOORD 0 in fragment shader by the expression float2 TEXCOORD 0 .x 1.0 TEXCOORD 0 .y .

After the texture unit coordinates are corrected point sprite emulator synthesizes the gl FragCoord variable containing window relative coordinates x y z and 1 w for fragment shader . In one embodiment such as HLSL supporting Shader Model 3.0 or greater gl FragCoord is synthesized from a variable using D3D s VPOS semantic. In another embodiment gl FragCoord is synthesized based on the projected location of the vertex in the viewport.

During the rasterization process the point sprite described using a vertex in 3D point set is converted into pixels for a display on a display screen or for storage in a bitmap file. In an ESSL vertex shader the width and height in pixels of the point sprite are controlled by writing to the gl PointSize variable. Point sprite emulator translates the gl PointSize variable in vertex shader into a variable in vertex shader using HLSL s PSIZE semantic.

Going back to GPU is a specialized microprocessor that accelerates real time computer graphics display on client . GPU may be located on a graphics card on client . GPU efficiently renders real time computer graphics due to its highly parallel architecture that is adept at processing complex mathematical algorithms common in graphics calculations.

GPU renders and re renders a webpage from resources . As part of the rendering process GPU also generates point sprites using 3D point sprite set and for example vertex shader and fragment shader and displays the point sprites on the display screen.

Processor is any conventional or special purpose processor including but not limited to digital signal processor DSP field programmable gate array FPGA and application specific integrated circuit ASIC . Processor executes applications such as browser .

At stage a command translation module receives a point sprite data and corresponding shaders. For example command translation module receives 3D point set vertex shader and fragment shader .

At stage a determination is made as to whether the shaders require translation. For example command translation module determines whether vertex shader and fragment shader written in ESSL language are compatible with client s platform environment. If vertex shader and fragment shader are compatible translation is not required and the method proceeds to stage . Otherwise the method proceeds to stage .

At stage the shaders are translated. For example emulator translates vertex shader written in ESSL into vertex shader written in HLSL and fragment shader written in ESSL into fragment shader written in HLSL. If vertex shader and fragment shader include instructions that generate point sprites point sprite emulator translates the instructions pertaining to point sprites. described herein is a flowchart of a method for translating vertex shader into vertex shader and fragment shader into fragment shader so that point sprites may be rendered after the translation.

At stage GPU processes the rendering instructions included in the shaders. For example GPU processes rendering data and rendering instructions and displays the result on a display screen.

At stage the point sprite render state D3DRS POINTSPRITEENABLE is enabled. The D3DRS POINTSPRITEENABLE render state allows a graphics card that understands the D3D API to generate point sprites using shaders written in HLSL.

At stage varying variables are transferred between the vertex shader and fragment shader so that their values are preserved. For example varying variables are transferred using the color units such as COLOR n .

At stage a fragment position within a point sprite is determined. For example gl PointCoord variable is synthesized from the zeroth texture unit s texture coordinate within the fragment shader .

At step the differences in the coordinate axis are corrected. For example point sprite emulator flips the vertical texture coordinate of the gl PointCoord variable in fragment shader so that it is computed from the expression float2 TEXCOORD 0 .x 1.0 TEXCOORD 0 .y in fragment shader .

At step the fragment coordinates are synthesized. For example point sprite emulator synthesizes the gl FragCoord variable referenced in fragment shader in fragment shader as described herein.

At step the point size of each pixel is translated. For example point sprite emulator translates an assignment to the gl PointSize variable in ESSL in vertex shader to an assignment to a variable with the PSIZE semantic in HLSL in vertex shader .

Web server and client can include one or more computing devices. According to an embodiment web server and client can include one or more processors one or more non volatile storage mediums and one or more memory devices a communication infrastructure a display screen and a communication interface . Processors can include any conventional or special purpose processor including but not limited to digital signal processor DSP field programmable gate array FPGA and application specific integrated circuit ASIC .

GPU is a specialized processor that executes instructions and programs selected for complex graphics and mathematical operations in parallel.

Non volatile storage can include one or more of a hard disk drive flash memory and like devices that can store computer program instructions and data on computer readable media. One or more of non volatile storage device can be a removable storage device. Memory devices can include one or more volatile memory devices such as but not limited to random access memory. Communication infrastructure can include one or more device interconnection buses such as Ethernet Peripheral Component Interconnect PCI and the like.

Typically computer instructions executing on web server or client are executed using one or more processors and can be stored in non volatile storage medium or memory devices .

Display screen allows results of the computer operations to be displayed to a user or an application developer.

Communication interface allows software and data to be transferred between computer system and external devices. Communication interface may include a modem a network interface such as an Ethernet card a communication port a PCMCIA slot and card or the like. Software and data transferred via communication interface may be in the form of signals which may be electronic electromagnetic optical or other signals capable of being received by communication interface . These signals may be provided to communication interface via a communication path. A communication path carries signals and may be implemented using wire or cable fiber optics a phone line a cellular phone link an RF link or other communications channels.

Embodiments may also be directed to computer program products comprising software stored on any computer useable medium. Such software when executed in one or more data processing device causes a data processing device s to operate as described herein. Embodiments of the invention employ any computer useable or readable medium. Examples of computer useable mediums include but are not limited to primary storage devices e.g. any type of random access memory secondary storage devices e.g. hard drives floppy disks CD ROMS ZIP disks tapes magnetic storage devices and optical storage devices MEMS nanotechnological storage device etc. .

The embodiments have been described above with the aid of functional building blocks illustrating the implementation of specified functions and relationships thereof. The boundaries of these functional building blocks have been arbitrarily defined herein for the convenience of the description. Alternate boundaries can be defined so long as the specified functions and relationships thereof are appropriately performed.

The foregoing description of the specific embodiments will so fully reveal the general nature of the invention that others can by applying knowledge within the skill of the art readily modify and or adapt for various applications such specific embodiments without undue experimentation without departing from the general concept of the present invention. Therefore such adaptations and modifications are intended to be within the meaning and range of equivalents of the disclosed embodiments based on the teachings and guidance presented herein. It is to be understood that the phraseology or terminology herein is for the purpose of description and not of limitation such that the terminology or phraseology of the present specification is to be interpreted by the skilled artisan in light of the teachings and guidance.

The Summary section may set forth one or more but not all exemplary embodiments as contemplated by the inventor s and thus are not intended to limit the present invention and the appended claims in any way.

The breadth and scope of the present invention should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the following claims and their equivalents.

