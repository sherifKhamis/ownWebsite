<template>
  <div class="app p-20">
    <!-- Hauptüberschrift der Portfolio-Webseite -->
    <h1 class="text-black text-2xl font-bold">Willkommen auf meiner Portfolio-Webseite</h1>
    <h2 class="text-gray-500 text-2xl">Meine Leidenschaft gilt Software und Daten.</h2>

    <!-- "Über mich" Sektion -->
    <h3 class="text-xl font-semibold text-center text-gray-800 mt-10" id="ueber-mich">Über mich</h3>

    <div class="flex flex-col md:flex-row items-center justify-center gap-20 mt-6">
      <!-- Profilbild -->
      <img 
        src="/images/profile.jpg" 
        alt="Profilbild" 
        class="w-1/3 rounded-xl shadow-lg"
      />

      <!-- Stichpunktliste mit persönlichen Informationen -->
      <ul class="w-2/3 list-disc list-outside text-lg text-gray-700 pl-5">
        <li>Alter: {{ age }}</li>
        <li>Aufgewachsen im schönen Hamburg</li>
        <li>Derzeit wohnhaft in Esslingen, Baden-Württemberg</li>
        <li>Besonderes Interesse an den Branchen: Automobil, Luft- und Raumfahrt und Telekommunikation</li>
        <li>Ein Teamplayer</li>
      </ul>
    </div>

    <!-- Qualifikation Sektion -->
    <h3 class="text-xl font-semibold text-center text-gray-800 mt-16" id="qualifikation">Qualifikation</h3>

    <div class="flex flex-col md:flex-row items-center justify-center gap-20 mt-6">
      <!-- Ausbildung als Fachinformatiker für Daten- und Prozessanalyse -->
      <div class="w-2/3">
        <h4 class="text-lg font-semibold text-gray-700">Ausbildung zum Fachinformatiker für Daten- und Prozessanalyse bei der Mercedes-Benz AG</h4>
        <p class="text-gray-600 mt-2 text-lg">
          Während meiner Ausbildung habe ich Grundlagen in verschiedenen Bereichen der Informatik vermittelt bekommen. Anschließend habe ich verschiedene spannende Abteilungen durchlaufen:
        </p>
        <ul class="list-disc list-outside text-lg text-gray-700 pl-5 mt-4">
          <li>IT-Entwicklung (ITD/OE): Software-Entwicklung mit Python, MS Azure und Github Actions</li>
          <li>Supply-Chain Management (SC/WTL): Datenanalyse mit MS Power BI und MS Excel</li>
          <li>Entwicklung (RD/AFL): Software-Entwicklung mit Python, Vue.js und Flutter</li>
        </ul>
      </div>
      <!-- Bild zu dieser Qualifikation -->
      <img 
        src="/images/DataAnalysis.jpg" 
        alt="Fachinformatiker für Daten- und Prozessanalyse" 
        class="w-1/3 rounded-xl bg-transparent"
      />
    </div>

    <div class="flex flex-col md:flex-row items-center justify-center gap-20 mt-6">
      <!-- Bild zur akademischen Qualifikation -->
      <img 
        src="/images/university-hat.jpg" 
        alt="Bachelorstudium der Informatik" 
        class="w-1/3 rounded-xl"
      />

      <!-- Informationen zum Bachelorstudium -->
      <div class="w-2/3">
        <h4 class="text-lg font-semibold text-gray-700">Bachelorstudium der Informatik an der IU Internationale Hochschule</h4>
        <p class="text-gray-600 mt-2 text-lg">
          Während meines berufsbegleitenden Studiums konnte ich mehr über die theoretischen Inhalte der Informatik lernen, mein Wissen vertiefen und meinen langfristigen Zielen ein Stück näher kommen.
        </p>
        <ul class="list-disc list-outside text-lg text-gray-700 pl-5 mt-4">
          <li>Schwerpunkt: Software-Engineering</li>
          <li>Durchschnittsnote: 2,4</li>
        </ul>
      </div>
    </div> 
    <!-- Navigationsleiste -->
    <Navbar />
  </div>
</template>

<script>
import { computed } from "vue";
import Navbar from './components/Navbar.vue';

// Geburtsdatum des Nutzers zur Altersberechnung
const birthDate = new Date(2001, 4, 21); // Monat ist 0-basiert (4 = Mai)

export default {
  name: "App",
  components: {
    Navbar,
  },
  setup() {
    // Berechnung des Alters anhand des aktuellen Datums
    const age = computed(() => {
      const today = new Date();
      let age = today.getFullYear() - birthDate.getFullYear();
      const monthDiff = today.getMonth() - birthDate.getMonth();
      const dayDiff = today.getDate() - birthDate.getDate();
      
      // Falls der Geburtstag dieses Jahr noch nicht war, Alter um 1 reduzieren
      if (monthDiff < 0 || (monthDiff === 0 && dayDiff < 0)) {
        age--;
      }
      
      return age;
    });

    return { age };
  },
};
</script>
