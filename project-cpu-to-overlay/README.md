# CPU Usage on Overlay

This project uses the [FixedIT Data Agent](https://fixedit.ai/products-data-agent/) to show the live CPU usage of an Axis camera directly in the video image.

The CPU usage is measured continuously and drawn as a graph in a video overlay, so you can see how hard the camera is working without opening any other tool. The same value is also printed in the Logs tab of the FixedIT Data Agent.

This is useful when a camera runs several applications at the same time, such as analytics or other ACAPs. If the CPU is close to full, the camera can become slow or drop frames, and the graph makes that visible right away.

The project also shows how the FixedIT Data Agent can control the Axis device itself, in this case by updating an overlay, and not only collect data and send it somewhere else.
