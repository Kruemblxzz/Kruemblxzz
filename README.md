<h1 id="typewriter"></h1>

<script>
const text = "As fast as a gallimus";
let i = 0;
function type() {
  if (i < text.length) {
    document.getElementById("typewriter").textContent += text.charAt(i);
    i++;
    setTimeout(type, 100);
  }
}
type();
</script>
<img width="258" height="402" alt="Image" src="https://github.com/user-attachments/assets/e22d7d3d-4407-4c9e-a7fb-d7d4fae435e3" />
