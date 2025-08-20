# Pisca LED com Arduino (Pin 10)

Projeto simples em **C++ usando o framework Arduino**, ideal para iniciantes testarem a IDE, a porta serial e o fluxo de upload de sketches.

## 🔧 Componentes
- 1× Arduino (Uno/Nano/MEGA, etc.)
- 1× LED 5 mm (qualquer cor)
- 1× Resistor **220 Ω a 1 kΩ** (sugestão: 330 Ω)
- Jumpers e, opcionalmente, uma protoboard

## 🧭 Esquema de Ligação
| Arduino | Componente | Observação |
|---|---|---|
| **D10** | **Resistor → Anodo (+) do LED** | Série entre o pino e o LED |
| **GND** | **Cátodo (–) do LED** | Vai direto ao GND |

> O lado **mais comprido** do LED é o **anodo (+)**.  
> O resistor pode ficar **antes ou depois** do LED (em série).

## 🧩 Código (piscaLED.ino)
```cpp
void setup() {
  pinMode(10, OUTPUT);
}

void loop() {
  digitalWrite(10, HIGH);
  delay(200);
  digitalWrite(10, LOW);
  delay(200);
}
```

- O LED acende por **200 ms** e apaga por **200 ms**, repetidamente.  
- Se quiser usar o **LED onboard** (pino **13**), troque `10` por `LED_BUILTIN`.

## ▶️ Como executar
1. Abra a **Arduino IDE**.
2. Selecione **Placa** e **Porta** corretas (Ferramentas → Placa/Porta).
3. Carregue o sketch `piscaLED.ino`.
4. O LED deve começar a piscar imediatamente.

## ⚙️ Personalizações rápidas
- **Velocidade do pisca:** ajuste os `delay(200)`.  
- **Pino do LED:** altere `pinMode(10, OUTPUT)` e `digitalWrite(10, ...)`.  
- **Padrão de pisca:** use diferentes delays ou `millis()` para evitar travas.

## 📁 Estrutura do repositório
```
pisca-led/
├─ piscaLED.ino
├─ README.md
├─ LICENSE
└─ .gitattributes
```

## 📝 Licença
Este projeto está sob a licença MIT – veja o arquivo [LICENSE](LICENSE) para mais detalhes.
