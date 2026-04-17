# 🏁 WRC History — Componente `Carrossel`

Um componente interativo em **Next.js / React** que apresenta a história dos carros mais icônicos do Campeonato Mundial de Rali (WRC), com ficha técnica, pilotos notáveis, curiosidades e vídeos.

---

## 📸 Visão Geral

O componente exibe uma barra horizontal com ícones dos carros. Ao clicar em um ícone, um painel lateral se abre com:

- Imagem e nome do carro (com cor temática da equipe)
- Anos de competição e categoria
- Descrição histórica
- Ficha técnica (motor, potência, tração, títulos WRC)
- Pilotos notáveis
- Curiosidade destacada
- Player de vídeo sob demanda

---

## 📁 Estrutura de Arquivos

```
components/
└── Carrossel/
    ├── Carrossel.tsx         # Componente principal
    ├── Carrossel.module.css  # Estilos CSS Modules
    └── VideoPlayer.tsx       # Subcomponente de vídeo

data/
└── carros.json               # Base de dados dos carros
```

---

## 🚗 Carros Incluídos

| ID | Carro |
|----|-------|
| `lancia-stratos` | Lancia Stratos |
| `audi-quattro` | Audi Quattro |
| `toyota-celica` | Toyota Celica |
| `lancia-delta` | Lancia Delta Integrale |
| `peugeot-205` | Peugeot 205 T16 |
| `citroen-c4` | Citroën C4 WRC |
| `subaru-impreza` | Subaru Impreza WRC |
| `mitsubishi-lancer-evo` | Mitsubishi Lancer Evolution |
| `renault-5` | Renault 5 Turbo |
| `ford-fiesta-wrc` | Ford Fiesta WRC |
| `toyota-gr-yaris` | Toyota GR Yaris Rally1 |
| `hyundai-i20n` | Hyundai i20 N Rally1 |

---

## 🗂️ Estrutura do `carros.json`

Cada entrada no arquivo JSON deve seguir a interface abaixo:

```ts
interface Carro {
  id: string;           // Identificador único (ex: "audi-quattro")
  nome: string;         // Nome de exibição
  anos: string;         // Período de competição (ex: "1980–1984")
  categoria: string;    // Categoria (ex: "Grupo B", "WRC", "Rally1")
  motor: string;        // Especificação do motor
  potencia: string;     // Potência (ex: "500 cv")
  tração: string;       // Tipo de tração (ex: "AWD", "RWD")
  campeonatos: number;  // Número de títulos WRC (0 se nenhum)
  pilotos: string[];    // Lista de pilotos notáveis
  descricao: string;    // Texto descritivo histórico
  curiosidade: string;  // Fato curioso sobre o carro
  cor: string;          // Cor temática em hex (ex: "#E30613")
  imagem: string;       // Caminho ou URL da imagem
  video: string;        // URL do vídeo (YouTube, etc.)
}
```

---

## ⚙️ Como Usar

### 1. Instale as dependências do projeto

```bash
npm install
# ou
yarn install
```

### 2. Adicione o componente à sua página

```tsx
import Carrossel from "@/components/Carrossel/Carrossel";

export default function Page() {
  return <Carrossel />;
}
```

### 3. Popule o arquivo de dados

Edite `data/carros.json` com os carros desejados seguindo a interface acima.

---

## 🎨 Personalização

- **Ordem dos carros:** Edite o array `ORDEM_IDS` em `Carrossel.tsx`
- **Cores temáticas:** Defina o campo `cor` em cada entrada do JSON — ele é aplicado no nome, badge e borda da curiosidade
- **Vídeos:** O campo `video` é repassado para o `VideoPlayer`; adapte esse componente conforme a plataforma utilizada (YouTube embed, etc.)

---

## 🛠️ Tecnologias

- [Next.js](https://nextjs.org/) (App Router)
- [React](https://react.dev/)
- [TypeScript](https://www.typescriptlang.org/)
- CSS Modules

---

## 📄 Licença

Este projeto é de uso livre para fins educacionais e pessoais.