//mostrar lista de amigos en pantalla
    const amigos = []; //array lista de amigos
    function mostrarAmigos() {
        let lista = document.getElementById("listaAmigos");
        lista.innerHTML = ""; //limpiar la lista al actualizar
        
        amigos.forEach(amigo => {
    lista.innerHTML += `<li>${amigo}</li>`;
  });
    }

// Función para agregar un amigo
function agregarAmigo() {
  const input = document.getElementById("amigo");
  const nombre = input.value.trim(); 

  // Validar que el campo no esté vacío
  if (nombre === "") {
    alert("Por favor, inserta un nombre.");
    return;
  }

  // Agregar al array
  amigos.push(nombre);

  // Mostrar lista actualizada
  mostrarAmigos();

  // Limpiar el campo de entrada
  input.value = "";
}
//Para sortear amigo
function sortearAmigo() {
if (amigos.length === 0) {
  alert("No hay amigos en la lista para sortear.");
  return;
}

const indiceAleatorio = Math.floor(Math.random()*amigos.length);

const amigoSorteado = amigos[indiceAleatorio];

const resultado = document.getElementById("resultado");
resultado.innerHTML = `<li>${amigoSorteado}</li>`;
}
