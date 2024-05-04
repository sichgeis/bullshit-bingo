<template>
  <div class="board">
    <BingoCard v-for="(title, idx) in titleList" :index="idx" :title="title" @flipped="onFlipped" />
  </div>
  <div v-if="showDetailModal" class="modal" @click="showDetailModal = false">
    <BingoCardDetail class="modal-content" :title="titleList[index]" :text="textList[index]" />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import BingoCard from './BingoCard.vue'
import BingoCardDetail from './BingoCardDetail.vue'

const titleList = [
  'Domain Specific Learning',
  'Prompt',
  'Training',
  'Context-Injection',
  'Pre-Training',
  'Fine-Tuning',
  'Zero-Shot Learning',
  'Few-Shot Learning',
  'One-Shot Learning',
  'RAG (Retrieval-Augmented Generation)',
  'Open Source Model',
  'Proprietary Model',
  'Function Calling',
  'Vector Datenbank',
  'Long-Term Memory',
  'Agents',
  'Hallucinations',
  'Inference Speed',
  'Time To First Token',
  'Coding Agents',
  'Knowledge Distillation',
  'Reinforcement Learning',
  'Transformer',
  'Unsupervised Learning',
  'Word Embedding',
]

const textList = [
  'Lernprozesse, die auf eine spezifische Domäne oder ein spezifisches Wissensgebiet ausgerichtet sind. Es wird darauf abgezielt, Modelle zu trainieren, die auf bestimmte Anwendungen oder Szenarien spezialisiert sind.',
  'Eine Eingabe oder Anfrage an ein KI-Modell, die als Startpunkt dient, um eine spezifische Antwort oder Ergebnis zu generieren.',
  'Der Prozess, bei dem ein künstliches neuronales Netzwerk anhand von Daten und Algorithmen trainiert wird, um Muster zu erkennen und spezifische Aufgaben auszuführen.',
  'Das Einbringen zusätzlicher, relevanter Informationen in das KI-Modell, um die Qualität der Antwort oder Vorhersage zu verbessern.',
  'Die Phase, in der ein KI-Modell mit einer großen Menge an allgemeinen Daten vor dem Feinabstimmen auf spezifische Aufgaben trainiert wird.',
  'Anpassung eines bereits vortrainierten Modells an eine spezifische Aufgabe oder einen spezifischen Datensatz, um die Leistungsfähigkeit auf diese spezielle Anwendung zu optimieren.',
  'Ein Ansatz im maschinellen Lernen, bei dem ein Modell Aufgaben ausführen kann, für die es keine spezifischen Trainingsdaten erhalten hat.',
  'Lernmethode, bei der das Modell nur mit einer sehr begrenzten Anzahl von Beispielen für jede Klasse trainiert wird.',
  'Ein Ansatz, bei dem ein Modell aus nur einem einzigen Trainingsbeispiel pro Klasse lernen kann.',
  'Ein Ansatz in der generativen KI, der Daten aus externen Quellen abruft, um informative und präzisere Antworten zu generieren.',
  'Ein KI-Modell, dessen Code und Trainingssätze öffentlich zugänglich und für die Nutzung und Modifikation durch die Gemeinschaft freigegeben sind.',
  'Ein kommerzielles KI-Modell, das von einem Unternehmen entwickelt wurde und dessen Nutzung typischerweise Lizenzgebühren oder bestimmte Nutzungsbedingungen unterliegt.',
  'In KI-Systemen die Fähigkeit, spezifische Funktionen oder Prozeduren innerhalb des Modells oder von externen Diensten auf Anfrage auszuführen.',
  'Spezialisierte Datenbank zur Speicherung und schnellen Suche von Vektoren, die in maschinellen Lernprozessen genutzt werden.',
  'Langzeitgedächtnis in KI-Systemen, das Informationen über längere Zeit speichert und zur Verbesserung der Leistung bei zukünftigen Aufgaben nutzt.',
  'Autonome Einheiten oder Softwareprogramme, die in der Lage sind, in einer Umgebung selbstständige Entscheidungen zu treffen und Aufgaben auszuführen.',
  'Falsche oder erfundene Informationen, die von einem KI-Modell generiert werden, oft als Resultat von Unsicherheiten im Trainingsdatensatz oder mangelnder Robustheit des Modells.',
  'Die Geschwindigkeit, mit der ein KI-Modell Eingaben verarbeitet und Antworten generiert.',
  'Die Zeit, die ein KI-Modell benötigt, um das erste Token (Wort oder Symbol) in einer Sequenz zu generieren.',
  'Spezialisierte Agenten in KI-Systemen, die für die Erstellung und Modifikation von Code zuständig sind.',
  'Ein Verfahren, bei dem Wissen von einem umfangreichen, komplexen Modell zu einem kleineren, effizienteren Modell übertragen wird.',
  'Ein Bereich des maschinellen Lernens, bei dem Algorithmen trainiert werden, optimale Handlungen auf Basis von Belohnungen und Strafen zu wählen, um ein bestimmtes Ziel zu erreichen.',
  'Ein Architekturtyp für neuronale Netzwerke, der besonders in der Verarbeitung von Sequenzen (z.B. Text) leistungsstark ist und auf Selbst-Attention-Mechanismen basiert.',
  'Ein Typ des maschinellen Lernens, bei dem das Modell aus Daten ohne vorherige Labels lernt, um Muster und Strukturen eigenständig zu erkennen.',
  'Die Darstellung von Wörtern in einem Vektorraum, die es ermöglicht, semantische Ähnlichkeiten zwischen verschiedenen Wörtern basierend auf ihrem Kontext zu erfassen.',
]

const showDetailModal = ref(false)
const index = ref<number | undefined>(undefined)

const onFlipped = (idx: number) => {
  console.log(`es wurde auf den index ${idx} gedrückt`);
  index.value = idx;
  showDetailModal.value = true;
}
</script>

<style scoped>
.board {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  gap: 0.7rem;

  @media only screen and (max-width: 600px) {
    gap: 0.2rem;
  }
}

.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(255, 255, 255, 0.4);
}

.modal-content {
  margin: 15% auto;
}
</style>
