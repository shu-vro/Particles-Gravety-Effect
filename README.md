# Particles-Gravety-Effect
Particles Gravety Effect  &lt;HTML> {CSS} (JavaScript)

`Hello, guys!`
Welcome to another episode of `Particles Effect` Where I will going to Design some cool particles Effect. I have More episodes which are: 
## Repos:
* [FireWork Particle Effect](https://github.com/shu-vro/Firework-Particle-Animation)
* [Particles Text Effect](https://github.com/shu-vro/Particles-Text-Effect)
* [Particles Effect Connectable](https://github.com/shu-vro/Particles-Effect_Connectable)
* [Particles Root Effect](https://github.com/shu-vro/Particles-Effect_2)
* [Particles Effect TRAIL](https://github.com/shu-vro/Particles-effect-TRAIL)
* [Image Particles Effect](https://github.com/shu-vro/Image-Particles-Effect)
* [Particles Effect](https://github.com/shu-vro/Particles-Effect)

### Templates That I used: 
``` JavaScript
const canvas = document.querySelector("canvas");
const ctx = canvas.getContext("2d");
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

let particles = [];

let mouse = {
    x: canvas.width / 2,
    y: canvas.height / 2,
};
window.addEventListener("mousemove", (e) => {
    mouse.x = e.clientX;
    mouse.y = e.clientY;
});
window.addEventListener("mouseout", () => {
    mouse.x = undefined;
    mouse.y = undefined;
});

class Particle {
    constructor(x, y, radius, color, velocity) {
        this.x = x;
        this.y = y;
        this.radius = radius;
        this.color = color;
        this.velocity = velocity;
    }
    draw() {
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2, false);
        ctx.fillStyle = this.color;
        ctx.fill();
    }
    update() {
        this.x += this.velocity.x;
        this.y += this.velocity.y;
        this.draw();
    }
}

function init() {
    particles = [];
    for (let i = 0; i < 50; i++) {
        let radius = Math.random() * 20 + 10;
        let x = Math.random() * canvas.width - radius;
        let y = Math.random() * canvas.height - radius;
        let color = `hsl(${Math.round(Math.random() * 360)}, 100%, 50%)`;
        let velocity = {
            x: Math.random() * 5 - 2.5,
            y: 0,
        }
        particles.push(new Particle(x, y, radius, color, velocity));
    }
}

function animate() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    particles.forEach((particle) => {
        particle.update();
    });
    requestAnimationFrame(animate);
}

init();
animate();

```
#### Keep Seeing And Enjoy.
