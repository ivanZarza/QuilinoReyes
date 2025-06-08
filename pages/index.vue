<script setup>
// No se requiere lógica JS para la presentación
</script>
<template>
  <div>
    <div class="presentacion">
      <div class="personal-container">
        <img src="/personal.jpg" class="personal" alt="Imagen de presentación" />
      </div>
      <div class="texto">
        <h1 class="text-center">De un Sueño a una Realidad.</h1>
        <p>
          Siempre soñé con pertenecer al mundo de la moda, con tener un nombre que la gente conociese, con crear una marca
          propia y dar a demostrar a la gente lo que puedo llegar a hacer con mi imaginación.<br>
          Hoy, todo ese sueño se ha convertido en una realidad, por primera vez puedo mostrar al mundo que gracias a mucho
          esfuerzo, constancia y perseverancia los sueños se hacen realidad y yo estoy cumpliendo el mío.
          Desde aquí ánimo a todas esas personas que tienen sueños que luchen por conseguirlos.<br>
          Os presento mi primera colección en la cual fusiono El Arte, La Cultura y El Flamenco. Tres características que
          me identifican por completo.
        </p>
        <button class="btn-gold" @click="$router.push('/corbatashombre')">Corbatas Hombre</button>
        <button class="btn-gold" @click="$router.push('/modahombre')">Moda Hombre</button>
        <button class="btn-gold" @click="$router.push('/modamujer')">Moda Mujer</button>
      </div>
    </div>
    <div class="divider"></div>
    <footer>
      <div class="footer">
        <div class="footer-texto">
          <h1>Formas de contacto</h1>
          <p><span class="icon-mail"></span> Correo: <a href="mailto:motesreyaquilino@gmail.com">motesreyaquilino@gmail.com</a></p>
          <p><span class="icon-phone"></span> Teléfono: <a href="tel:600815960">600 815 960</a></p>
          <p><span class="icon-ig"></span> Instagram: <a href="https://instagram.com/Quilinoreyes_moda_" target="_blank">Quilinoreyes_moda_</a></p>
          <h3>Se hacen envíos a toda España.</h3>
        </div>
      </div>
    </footer>
  </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Montserrat:wght@400;700&display=swap');

.presentacion {
  width: 90%;
  max-width: 900px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 2rem;
  margin: 40px auto 0 auto;
}
.personal-container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
}
.personal {
  width: 420px;
  height: auto;
  object-fit: cover;
  border: 3px solid goldenrod;
  box-shadow: 0 4px 24px 0 rgba(0,0,0,0.5);
  background-color: black;
  display: block;
}
.personal:hover {
  box-shadow: 0 8px 32px 0 rgba(218,165,32,0.3);
}
.texto {
  width: 100%;
  background: rgba(0,0,0,0.85);
  border-radius: 18px;
  padding: 2.5rem 2rem 2rem 2rem;
  color: #fff;
  font-size: 1.25rem;
  margin-bottom: 2rem;
  text-align: center;
  box-shadow: 0 2px 16px 0 rgba(0,0,0,0.2);
  border-bottom: 3px solid goldenrod;
  font-family: 'Montserrat', Arial, sans-serif;
}
.text-center {
  text-align: center;
  text-decoration: underline 2px solid goldenrod;
  font-size: 2.7rem;
  color: goldenrod;
  font-family: 'Playfair Display', serif;
  margin-bottom: 1rem;
}
.btn-gold {
  margin-top: 1.5rem;
  margin-right: 1.5rem;
  margin-left: 1.5rem;
  background: goldenrod;
  color: #181818;
  border: none;
  border-radius: 25px;
  padding: 0.7rem 2.2rem;
  font-size: 1.1rem;
  font-weight: bold;
  cursor: pointer;
  box-shadow: 0 2px 8px 0 rgba(218,165,32,0.15);
  transition: background 0.2s, color 0.2s, box-shadow 0.2s;
  letter-spacing: 1px;
  display: inline-block;
}
.btn-gold:last-child {
  margin-right: 0;
}
.btn-gold:hover {
  background: #fff;
  color: goldenrod;
  box-shadow: 0 4px 16px 0 rgba(218,165,32,0.25);
}
.divider {
  width: 100%;
  max-width: 900px;
  height: 2px;
  background: linear-gradient(90deg, transparent, goldenrod, transparent);
  margin: 2rem auto 1rem auto;
  border-radius: 2px;
  display: block;
}
.footer {
  padding: 30px 0 60px 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  color: goldenrod;
  font-size: 1.1rem;
  margin: 0;
}
.footer-texto {
  width: 100%;
  max-width: 500px;
  border: 1px solid goldenrod;
  padding: 20px;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
  background-color: #000;
  gap: 10px;
  opacity: 0.95;
  box-shadow: 0 2px 16px 0 rgba(0,0,0,0.2);
}
.footer-texto a {
  color: goldenrod;
  text-decoration: underline;
  transition: color 0.2s;
}
.footer-texto a:hover {
  color: #fff;
}
.icon-mail::before {
  content: '\2709';
  margin-right: 6px;
}
.icon-phone::before {
  content: '\260E';
  margin-right: 6px;
}
.icon-ig::before {
  content: '\1F4F7';
  margin-right: 6px;
}
@media (max-width: 900px) {
  .presentacion {
    width: 98%;
    gap: 1.2rem;
    flex-direction: column;
    align-items: center;
  }
  .personal {
    width: 120px;
    height: 120px;
  }
  .texto {
    font-size: 1rem;
    padding: 1.2rem 0.7rem 1.2rem 0.7rem;
  }
  .text-center {
    font-size: 1.5rem;
  }
  .btn-gold {
    display: block;
    width: 90%;
    margin: 1rem auto 0.5rem auto;
  }
}

@media (max-width: 600px) {
  .presentacion {
    width: 100%;
    gap: 0.7rem;
  }
  .personal {
    width: 60%;
    height: auto;
  }
  .texto {
    font-size: 0.7rem;
    padding: 0.7rem 0.3rem 0.7rem 0.3rem;
    width: 90%;
  }
  .text-center {
    font-size: 1.1rem;
  }
  .footer-texto {
    font-size: 0.9rem;
    padding: 10px;
  }
  .btn-gold {
    width: 100%;
    font-size: 1rem;
    padding: 0.7rem 0;
    margin: 0.7rem 0 0 0;
  }
}
</style>