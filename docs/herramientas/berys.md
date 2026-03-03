---
layout: default
title: Berisso
---

<div class="tool-hero">
  <h1>Dashboard de Actividad De Berisso</h1>
  <p class="tool-subtitle">
    Sistema Integral de Recaudación y Análisis para el Municipio de Berisso.
  </p>
  <p>
    Tablero estratégico diseñado para supervisar la actividad recaudatoria, judicial y productiva vinculada a las fotomultas municipales.
  </p>
</div>

---

## Descripción General

<div class="section-block">

El sistema centraliza información clave sobre la gestión de presunciones e infracciones en el Municipio de Berisso, permitiendo el análisis integral de la actividad administrativa, judicial y productiva.

Facilita la toma de decisiones mediante indicadores claros, métricas comparativas y visualizaciones orientadas a la optimización de recursos y procesos.

</div>

---

## Funcionalidades Principales

<div class="feature-grid">

<div class="feature-item">
<h3>Actividad Recaudatoria</h3>
<p>Seguimiento detallado de ingresos generados por fotomultas, evolución temporal y comparación entre períodos.</p>
</div>

<div class="feature-item">
<h3>Actividad Judicial</h3>
<p>Análisis del estado procesal de las infracciones, evolución de causas y métricas de resolución.</p>
</div>

<div class="feature-item">
<h3>Actividad Productiva</h3>
<p>Monitoreo del volumen de actas generadas, procesamiento de infracciones y desempeño operativo.</p>
</div>

<div class="feature-item">
<h3>Gestión de Usuarios</h3>
<p>Control de accesos, perfiles y seguimiento de actividad dentro del sistema.</p>
</div>

</div>

---

## Gestión de Notificaciones

<div class="section-block">

<h3>Lotes de Notificación</h3>
<p>Visualización y seguimiento de los lotes de notificaciones entregadas en la Municipalidad de Berisso.</p>

<h3>Estado y Trazabilidad</h3>
<p>Control del estado de cada lote, fechas de emisión y confirmación de recepción.</p>

<h3>Histórico de Entregas</h3>
<p>Acceso a registros históricos para auditoría y control administrativo.</p>

</div>

---

## Análisis Estratégico

<div class="section-block">

<h3>Métricas Comparativas</h3>
<p>Comparación entre períodos mensuales, trimestrales y anuales para detectar tendencias.</p>

<h3>Indicadores Clave (KPIs)</h3>
<p>Panel de control con métricas fundamentales para la gestión financiera y operativa.</p>

<h3>Visualización Dinámica</h3>
<p>Gráficos interactivos que permiten explorar datos por rango de fechas, tipo de infracción o estado judicial.</p>

</div>
## Vista del Producto

<div class="carousel">
  <div class="slides">
    <img src="{{ '/assets/img/BeryIndex.png' | relative_url }}" alt="Dashboard principal">
    <img src="{{ '/assets/img/PaymentsBerys.png' | relative_url }}" alt="Pagos">
    <img src="{{ '/assets/img/LotesBerys.png' | relative_url }}" alt="Lotes Notificaciones">
    <img src="{{ '/assets/img/FallosBerys.png' | relative_url }}" alt="Lotes Notificaciones">
  </div>
</div>

<!-- LIGHTBOX -->
<div id="lightbox" class="lightbox">
  <span class="close">&times;</span>
  <img class="lightbox-img">
</div>

<script>
document.addEventListener("DOMContentLoaded", function() {

  const images = document.querySelectorAll(".slides img");
  const lightbox = document.getElementById("lightbox");
  const lightboxImg = document.querySelector(".lightbox-img");
  const closeBtn = document.querySelector(".close");

  images.forEach(img => {
    img.addEventListener("click", () => {
      lightbox.style.display = "flex";
      lightboxImg.src = img.src;
    });
  });

  function closeLightbox() {
    lightbox.style.display = "none";
  }

  closeBtn.addEventListener("click", closeLightbox);

  lightbox.addEventListener("click", (e) => {
    if (e.target !== lightboxImg) {
      closeLightbox();
    }
  });

  document.addEventListener("keydown", (e) => {
    if (e.key === "Escape") {
      closeLightbox();
    }
  });

});
</script>
