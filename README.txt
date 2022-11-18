MID files converted to JSON using https://tonejs.github.io/Midi/


function parseFile(file) {
				//read the file
				const reader = new FileReader();
				reader.onload = function (e) {
					const midi = new Midi(e.target.result);
					document.querySelector(
						"#ResultsText"
					).value = JSON.stringify(midi, undefined, 2);
					document
						.querySelector("tone-play-toggle")
						.removeAttribute("disabled");
					currentMidi = midi;
				};
				reader.readAsArrayBuffer(file);
			}
