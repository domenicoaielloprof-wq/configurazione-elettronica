<!doctype html>
<html lang="it">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Configurazione elettronica</title>
  <style>
    body {
      max-width: 900px;
      margin: 2rem auto;
      padding: 0 1rem;
      font-family: Arial, sans-serif;
      line-height: 1.5;
    }

    label, input, button {
      font-size: 1rem;
    }

    input {
      width: 8rem;
      padding: 0.4rem;
      margin: 0.5rem 0.5rem 0.5rem 0;
    }

    button {
      padding: 0.45rem 0.8rem;
      cursor: pointer;
    }

    .risultato {
      margin-top: 1.25rem;
      padding: 1rem;
      border: 1px solid #777;
      border-radius: 0.4rem;
    }

    .gruppo {
      margin: 0.75rem 0;
    }

    .caselle {
      display: flex;
      flex-wrap: wrap;
      gap: 0.35rem;
      margin-top: 0.25rem;
    }

    .casella {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      min-width: 2.4rem;
      height: 2rem;
      border: 1px solid #333;
      font-family: monospace;
      font-size: 1.1rem;
    }

    .nota {
      color: #444;
      font-size: 0.95rem;
    }
  </style>
</head>
<body>
  <h1>Generatore di configurazioni elettroniche</h1>
  <p>
    Inserisci il numero atomico di un atomo neutro. Il programma mostra la
    configurazione e le caselle orbitali secondo l’ordine di riempimento
    scolastico semplificato.
  </p>

  <label for="numeroAtomico">Numero atomico:</label>
  <input id="numeroAtomico" type="number" min="1" max="118" value="8">
  <button id="genera" type="button">Genera</button>

  <section id="risultato" class="risultato" aria-live="polite">
    <p>Inserisci un numero atomico e seleziona “Genera”.</p>
  </section>

  <script>
    const sottolivelli = [
      { nome: "1s", orbitali: 1 },
      { nome: "2s", orbitali: 1 },
      { nome: "2p", orbitali: 3 },
      { nome: "3s", orbitali: 1 },
      { nome: "3p", orbitali: 3 },
      { nome: "4s", orbitali: 1 },
      { nome: "3d", orbitali: 5 },
      { nome: "4p", orbitali: 3 },
      { nome: "5s", orbitali: 1 },
      { nome: "4d", orbitali: 5 },
      { nome: "5p", orbitali: 3 },
      { nome: "6s", orbitali: 1 },
      { nome: "4f", orbitali: 7 },
      { nome: "5d", orbitali: 5 },
      { nome: "6p", orbitali: 3 },
      { nome: "7s", orbitali: 1 },
      { nome: "5f", orbitali: 7 },
      { nome: "6d", orbitali: 5 },
      { nome: "7p", orbitali: 3 }
    ];

    function costruisciConfigurazione(numeroAtomico) {
      let elettroniRimasti = numeroAtomico;
      const occupazioni = [];

      for (const sottolivello of sottolivelli) {
        if (elettroniRimasti <= 0) break;

        const capienza = sottolivello.orbitali * 2;
        const elettroni = Math.min(elettroniRimasti, capienza);

        occupazioni.push({
          nome: sottolivello.nome,
          orbitali: sottolivello.orbitali,
          elettroni: elettroni
        });

        elettroniRimasti -= elettroni;
      }

      return occupazioni;
    }

    function creaDiagramma(occupazione) {
      const elettroniPerOrbitale = Array(occupazione.orbitali).fill(0);
      let rimasti = occupazione.elettroni;

      // Regola di Hund: prima un elettrone per orbitale.
      for (let i = 0; i < elettroniPerOrbitale.length && rimasti > 0; i++) {
        elettroniPerOrbitale[i]++;
        rimasti--;
      }

      // Poi si appaiano gli elettroni con spin opposto.
      for (let i = 0; i < elettroniPerOrbitale.length && rimasti > 0; i++) {
        elettroniPerOrbitale[i]++;
        rimasti--;
      }

      return elettroniPerOrbitale.map(numero => {
        if (numero === 2) return "↑↓";
        if (numero === 1) return "↑";
        return " ";
      });
    }

    function mostraRisultato() {
      const campo = document.getElementById("numeroAtomico");
      const area = document.getElementById("risultato");
      const numeroAtomico = Number(campo.value);

      if (!Number.isInteger(numeroAtomico) ||
          numeroAtomico < 1 ||
          numeroAtomico > 118) {
        area.textContent = "Inserisci un numero intero compreso tra 1 e 118.";
        return;
      }

      const occupazioni = costruisciConfigurazione(numeroAtomico);
      const configurazione = occupazioni
        .map(voce => `${voce.nome}<sup>${voce.elettroni}</sup>`)
        .join(" ");

      area.replaceChildren();

      const intestazione = document.createElement("h2");
      intestazione.textContent = `Numero atomico ${numeroAtomico}`;
      area.appendChild(intestazione);

      const rigaConfigurazione = document.createElement("p");
      rigaConfigurazione.innerHTML = `<strong>Configurazione:</strong> ${configurazione}`;
      area.appendChild(rigaConfigurazione);

      const titoloCaselle = document.createElement("h3");
      titoloCaselle.textContent = "Diagramma a caselle";
      area.appendChild(titoloCaselle);

      for (const voce of occupazioni) {
        const gruppo = document.createElement("div");
        gruppo.className = "gruppo";

        const etichetta = document.createElement("strong");
        etichetta.textContent = `${voce.nome}: `;
        gruppo.appendChild(etichetta);

        const caselle = document.createElement("div");
        caselle.className = "caselle";

        for (const contenuto of creaDiagramma(voce)) {
          const casella = document.createElement("span");
          casella.className = "casella";
          casella.textContent = contenuto;
          caselle.appendChild(casella);
        }

        gruppo.appendChild(caselle);
        area.appendChild(gruppo);
      }

      const nota = document.createElement("p");
      nota.className = "nota";
      nota.textContent =
        "Modello didattico semplificato: non considera ioni, stati eccitati " +
        "né eccezioni alla sequenza generale di riempimento.";
      area.appendChild(nota);
    }

    document.getElementById("genera")
      .addEventListener("click", mostraRisultato);

    document.getElementById("numeroAtomico")
      .addEventListener("keydown", evento => {
        if (evento.key === "Enter") mostraRisultato();
      });

    mostraRisultato();
  </script>
</body>
</html>
