---
layout: default
title: T.A.I
---

<div class="tool-hero">
  <h1>T.A.I</h1>
  <p class="tool-subtitle">
    Sistema De Análisis de Apremios.
  </p>
  <p>
    Dashboard estratégico diseñado para el seguimiento integral de juicios en situación de apremio, permitiendo control, análisis y trazabilidad del proceso judicial.
  </p>
</div>

---

## Descripción General

<div class="section-block">

T.A.I centraliza la información vinculada a juicios de apremio, facilitando el monitoreo completo del ciclo de vida judicial, desde su inicio hasta su resolución o cobro efectivo.

El sistema integra métricas operativas, estadísticas comparativas y consultas detalladas, brindando una visión clara del estado actual de la cartera judicial.

</div>

---

## Seguimiento del Ciclo de Vida

<div class="feature-grid">

<div class="feature-item">
<h3>Inicio de Juicios</h3>
<p>Registro y contabilización de juicios iniciados por período, tipo de deudor y categoría de infracción.</p>
</div>

<div class="feature-item">
<h3>Estado Procesal</h3>
<p>Visualización del estado actualizado de cada juicio: iniciado, en trámite, en ejecución, cancelado o finalizado.</p>
</div>

<div class="feature-item">
<h3>Juicios Cobrados</h3>
<p>Identificación y seguimiento de expedientes con cobro efectivo, permitiendo análisis de recupero.</p>
</div>

<div class="feature-item">
<h3>Cierre y Resolución</h3>
<p>Control de finalización del proceso judicial con trazabilidad documental completa.</p>
</div>

</div>

---

## Análisis Estadístico

<div class="section-block">

<h3>Indicadores Generales</h3>
<p>Métricas consolidadas sobre cantidad total de juicios iniciados, activos, cobrados y pendientes.</p>

<h3>Personas Físicas y Jurídicas</h3>
<p>Estadísticas segmentadas por tipo de deudor para análisis comparativo y evaluación de comportamiento de pago.</p>

<h3>Evolución Temporal</h3>
<p>Visualización de tendencias mensuales y anuales en la gestión de apremios.</p>

</div>

---

## Consultas y Control Documental

<div class="section-block">

<h3>Consultas Detalladas</h3>
<p>Búsqueda avanzada de expedientes por número de juicio, CUIT/DNI, estado procesal o rango de fechas.</p>

<h3>Recibos de Pago</h3>
<p>Acceso digital a comprobantes de pago asociados a juicios cancelados, garantizando respaldo documental y auditoría.</p>

<h3>Trazabilidad Completa</h3>
<p>Registro histórico de cada movimiento realizado sobre el expediente judicial.</p>

</div>

---

## Gestión Estratégica

<div class="section-block">

<h3>Recupero de Deuda</h3>
<p>Análisis del rendimiento del proceso de apremio en términos de recupero financiero.</p>

<h3>Control Operativo</h3>
<p>Supervisión del volumen de juicios activos y eficiencia en la gestión judicial.</p>

<h3>Soporte a la Toma de Decisiones</h3>
<p>Información consolidada para planificación jurídica y administrativa.</p>

</div>

## Vista del Producto

<div class="carousel">
  <div class="slides">
    <img src="{{ '/assets/img/TAIlogin.png' | relative_url }}" alt="Login">
    <img src="{{ '/assets/img/TAIindex.png' | relative_url }}" alt="Pagina principal">
    <img src="{{ '/assets/img/TAIquery.png' | relative_url }}" alt="Consulta detallada">
    <img src="{{ '/assets/img/TAIreceipt.png' | relative_url }}" alt="Recibos">
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
</script>
