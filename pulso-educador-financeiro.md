# PULSO — seu copiloto financeiro

Proposta de um Educador Financeiro Inteligente para jovens que estão começando a trabalhar.

---

## 1. Para quem é

Jovens de **18 a 26 anos**, no primeiro ou segundo emprego, com renda entre **R$ 1.500 e R$ 4.000**, que chegam ao dia 25 do mês sem saber para onde foi o dinheiro.

**Problema central:** gastar mais do que ganha, sem perceber onde está o vazamento.

**Promessa em uma frase:**
> "Você me diz quanto ganha. Eu te mostro, em 10 segundos por dia, quanto ainda dá para gastar."

---

## 2. Tom da comunicação

Futurista no visual e na velocidade — números que reagem na hora, leitura por cores, sensação de sistema ligado. Amigável no texto — nada de jargão.

**O sistema fala assim:**

- "Sobrou R$ 312 para os 9 dias que faltam. Dá R$ 34 por dia."
- "Delivery já passou o limite do mês. Foram 7 pedidos, R$ 280."
- "Se você guardar R$ 150 por mês, o notebook chega em novembro."

**O sistema nunca fala assim:**

- "Sua alocação de recursos apresenta desequilíbrio na categoria alimentação fora do lar."
- "Recomenda-se a constituição de reserva equivalente a 6 meses de despesas correntes."

---

## 3. Funcionalidades principais

### 3.1 Painel simples de gastos — o "modo semáforo"

O usuário não preenche planilha. Ele responde uma pergunta por dia: *"Gastou algo hoje?"* e escolhe entre 6 categorias com ícone.

Cada categoria vira uma barra colorida:

| Cor | Significado |
|---|---|
| Verde | Dentro do combinado |
| Amarelo | Passou de 75% do limite |
| Vermelho | Estourou o limite |

No topo da tela, um único número grande: **quanto ainda dá para gastar até o fim do mês**. É o dado que importa.

**Exemplo de painel:**

- Ainda dá para gastar: **R$ 312** (R$ 34 por dia até o dia 30)
- Entrou: R$ 1.800 · Saiu: R$ 1.488
- Moradia: R$ 600 / 600 · verde
- Transporte: R$ 210 / 250 · amarelo
- Delivery: R$ 280 / 180 · vermelho
- Lazer: R$ 150 / 300 · verde

---

### 3.2 Alertas de despesa exagerada

O alerta chega **no momento do gasto**, não no fim do mês, quando já não adianta.

**Alerta de repetição**
> "5º iFood da semana. Cozinhar 3 dessas noites economizaria R$ 90."

**Alerta de ritmo**
> "Estamos no dia 12 e você já usou 60% do mês. No ritmo atual, falta R$ 240 no dia 28."

**Alerta de compra grande** (acima de 10% da renda)
> "Isso é 1 dia e meio do seu salário. Quer esperar 24h antes de decidir?"

---

### 3.3 Simulador de metas

O usuário escolhe o objetivo e o app mostra o caminho em números concretos, não em porcentagem.

| Meta | Guardando por mês | Prazo | Equivale a |
|---|---|---|---|
| Fone R$ 600 | R$ 100 | 6 meses | 3 idas ao bar |
| Viagem R$ 2.400 | R$ 200 | 12 meses | 1 assinatura + 4 deliveries |
| Reserva de emergência R$ 4.500 | R$ 250 | 18 meses | R$ 8 por dia |

**Diferencial:** toda meta é traduzida em "o que você deixa de fazer", porque isso é o que a pessoa realmente sente.

---

## 4. Como a IA adapta as recomendações

O cadastro tem **4 perguntas**, nada mais: renda mensal, idade, com quem mora e um objetivo.

### Por renda

| Faixa | Foco da recomendação | Meta inicial sugerida |
|---|---|---|
| Até R$ 1.800 | Cortar vazamentos pequenos e repetidos (assinaturas, taxa de entrega, juros do rotativo) | R$ 50/mês |
| R$ 1.800 – R$ 3.000 | Reserva de emergência de 3 meses e separar o dinheiro no dia do pagamento | R$ 150/mês |
| Acima de R$ 3.000 | Automatizar a guarda e primeiro investimento simples | R$ 300/mês |

> Meta impossível faz a pessoa desistir. O valor inicial é sempre baixo o suficiente para ser cumprido no primeiro mês.

### Por idade e situação

- **18–21, mora com a família** → aproveitar a fase de custo fixo baixo: "guardar 20% agora vale mais do que guardar 20% daqui a 5 anos."
- **22–26, mora sozinho** → o alerta vira sobre custo fixo: "seu aluguel é 42% da renda. O saudável fica perto de 30%."

### Por objetivo

- **Curto prazo** (viagem, celular) → mostra o valor **por semana**, não por mês. Semana é o horizonte que jovem enxerga.
- **Longo prazo** (faculdade, sair de casa) → mostra o efeito de guardar cedo com um número, não com fórmula: "R$ 100/mês por 3 anos = R$ 3.600 guardados + R$ 480 de rendimento."

### Aprendizado embutido

Um conceito por semana, em 60 segundos, sempre ligado a algo que aconteceu na conta do usuário.

Quando ele paga o mínimo do cartão, o app explica juros rotativos **ali**, com o número dele. Conceito descolado da vida real não gruda.

---

## 5. Transformando em projeto frontend interativo

Da ideia mais simples à mais ambiciosa.

### 5.1 MVP em uma tela só
React + Tailwind, dados em `useState`. Painel + input de gasto + barra de meta. Sem backend, sem login. Dá para construir em um fim de semana e já demonstra o conceito inteiro.

### 5.2 Onboarding conversacional
Em vez de formulário, as 4 perguntas aparecem como um chat que digita sozinho. Cada resposta é um botão. Vende o "futurista" sem custar complexidade.

### 5.3 Registro em 3 toques
Botão flutuante → grid de 6 ícones de categoria → teclado numérico próprio, só dígitos grandes.
**Meta:** registrar um gasto em menos de 4 segundos. É a métrica de sucesso do produto inteiro.

### 5.4 Simulador com slider ao vivo
Slider de "quanto guardar por mês" que recalcula a data da meta em tempo real, sem botão de confirmar. Ver a data pular de "dezembro" para "setembro" ao arrastar é o momento em que a pessoa entende o poder da economia.

### 5.5 Semáforo animado
As barras crescem com transição e mudam de cor ao cruzar 75% e 100%. Um pulso sutil quando entra no vermelho. Animação com propósito, não decoração.

### 5.6 Modo "e se eu cortar isso?"
Toque em qualquer categoria e um painel mostra: "cortando 30% daqui, sua meta chega 2 meses antes." Transforma dado em decisão.

### 5.7 Gamificação leve
Sequência de dias registrados (streak), selos por metas batidas e um "nível financeiro" que sobe conforme o usuário aprende conceitos.
Sem competição com outras pessoas — o adversário é o mês passado.

### 5.8 Comparativo mês a mês
Gráfico de barras simples (Recharts) sobrepondo o mês atual ao anterior. A frase de topo faz o trabalho: "você gastou R$ 180 a menos que em julho."

### 5.9 Detalhes que dão o clima futurista sem exagero
- Tema escuro por padrão
- Tipografia monoespaçada só nos números
- Contadores que animam ao mudar de valor
- Microfeedback tátil (`navigator.vibrate`) ao registrar um gasto

### 5.10 Modo demo
Um botão "ver com dados de exemplo" que preenche um mês fictício completo. Essencial para apresentação, portfólio ou pitch — ninguém avalia um app financeiro vazio.

---

## 6. Stack sugerida para o protótipo

| Camada | Escolha | Por quê |
|---|---|---|
| Framework | React (Vite) | Rápido de subir, ecossistema conhecido |
| Estilo | Tailwind CSS | Prototipagem visual veloz |
| Gráficos | Recharts | Simples para barras e progresso |
| Ícones | Lucide React | Leve e consistente |
| Estado | `useState` / `useReducer` | Suficiente para o MVP, sem backend |
| Persistência | Backend simples ou armazenamento próprio do ambiente | Só quando sair do protótipo |

---

## 7. Métricas de sucesso do produto

1. **Tempo de registro de um gasto** — abaixo de 4 segundos
2. **Dias registrados por semana** — meta de 5 ou mais
3. **Usuários que batem a primeira meta** — meta de 40% em 90 dias
4. **Redução de gasto na categoria alertada** — meta de 15% no mês seguinte
