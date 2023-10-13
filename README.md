# WASM-in-Docker

### The Basic Structure

A docker image containing several useful WASM libraries recieves job requests containing a WASM executable followed by any input data. It responds to the client with any resulting output. If many people run this system on their PCs, it will enable developers to run small jobs for free without relying on large cloud service providers.

### Why WASM?

WASM modules are lighting fast to initialize, on the order of milliseconds. Depending on your code, they may also be lighting fast to run. Fortunately, microservice architectures are the standard these days, so small bite-sized jobs are common practice. Such small executables and rapid execution begins to make it more reasonable to recieve the job executable itself within requests. Since most WASM runtimes containerize the jobs they are running, multiple may safely and securely run concurrently on the same machine.

### Why Docker?

Docker, in combination with tools like Kubernetes, is the backbone of most microservice architectures today, and will continue to be. While docker images don't have to be updated and restarted as frequently when application logic is recieved anew each request, occaisionally it is still necessary to update the libraries, and Docker makes it easy to update an image once and restart servers everywhere a la continuous deployment. It is so easy, in fact, that servers may simply restart themselves periodically to stay reasonably up to date. Volunteer server hosts would scarcely need to do any active maintenance at all, and the barrier to entry is the floor.