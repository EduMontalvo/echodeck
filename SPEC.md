# Especificación Técnica: English App (Fase 1 - MVP)

## 1. Objetivo
Construir la base funcional de una plataforma web para aprendizaje de inglés mediante repetición espaciada (SRS estilo Anki) e Input Comprensible básico.

## 2. Stack Tecnológico
- Frontend: React, TypeScript, Tailwind CSS, Vite.
- Backend: Node.js, Express, TypeScript.
- ORM & Base de Datos: Prisma con SQLite (desarrollo local).

## 3. Alcance de la Fase 1
- Modelado de datos en Prisma:
  - `Deck` (id, title, description, createdAt, updatedAt).
  - `Flashcard` (id, word, translation, phonetic, contextPhrase, interval, repetition, easeFactor, nextReviewDate, deckId).
- API REST básica (Express):
  - `POST /api/decks`: Crear un mazo.
  - `GET /api/decks`: Listar mazos.
  - `POST /api/cards`: Crear una tarjeta manual asignada a un mazo.
  - `GET /api/cards/review?deckId=...`: Obtener tarjetas con `nextReviewDate <= now`.
  - `POST /api/cards/:id/review`: Registrar respuesta del usuario (Again, Good, Easy) y recalcular SM-2.
- Frontend (React):
  - Vista de lista de mazos.
  - Formulario simple para crear tarjetas.
  - Interfaz de estudio: mostrar el frente de la tarjeta (palabra + contexto), botón para voltear (ver traducción + fonética), y botones de calificación de dificultad.

## 4. Fuera de Alcance (No implementar en esta fase)
- Transcripción de audio o integración con Whisper.
- Parseo o descarga de videos de YouTube/archivos externos.
- Generación de audio por Text-to-Speech (TTS).
- Autenticación o roles de usuario complejos.