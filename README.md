# Projeto para a Dinâmica - Elas Protagonistas em IA

Bem-vindas ao nosso espaço de trabalho! Este repositório é o nosso centro de organização para a dinâmica. O objetivo é colaborar, registrar nossas ideias e construir juntas uma solução de IA Simbólica incrível. ✨

---

## 🗺️ Nosso Plano de Ação

Para garantir que usemos nosso tempo da melhor forma possível, vamos seguir um fluxo de trabalho claro e dividido em etapas.

### Sugestão de Cronograma (Total: 50 minutos)

-   **Etapa 1: Modelagem e Entendimento:** `10 minutos`
-   **Etapa 2: Construção da Lógica:** `5 minutos`
-   **Etapa 3: Codificação e Pitch:** `27 minutos`
-   **Etapa 4: Teste e Validação:** `8 minutos`

---

### 1. Modelagem e Entendimento do Problema

Nesta primeira fase, o foco é garantir que todas compreendemos o desafio por completo.

-   **Atividades:**
    -   Leitura atenta do case proposto.
    -   Brainstorm de ideias e possíveis abordagens.
    -   Definição e escrita das **regras de negócio** principais. (Ex: "SE o cliente for VIP E a compra > R$300, ENTÃO dar 20% de desconto").
    -   Tirar todas as dúvidas entre nós para estarmos 100% na "mesma página".
-   **Meta:** Ter um documento ou rascunho com as regras de negócio bem definidas e acordadas por todas.

### 2. Construção da Lógica (Pseudocódigo)


Antes de escrever qualquer linha de Python, vamos desenhar a lógica em conjunto.

-   **Atividades:**
    -   Escrever um pseudocódigo (em português mesmo) que represente o fluxo da nossa solução.
    -   Discutir as estruturas de dados que usaremos (listas, dicionários, etc.).
    -   "Testar" nosso pseudocódigo com 2 ou 3 exemplos de entrada para ver se as saídas são as esperadas.
-   **Meta:** Ter um esqueleto lógico claro que servirá como guia para a fase de codificação.

### 3. Codificação e Preparação do Pitch


Com o plano em mãos, agora é hora de dividir para conquistar!

-   **Atividades (em paralelo):**
    -   **Time de Código (1-3 pessoas):** Traduzir o pseudocódigo para Python, criando as funções e a lógica principal.
    -   **Time de Apresentação (1-3 pessoas):** Começar a estruturar o pitch de 7 minutos. Pode ser em 1 ou 2 slides (opcional) ou apenas um roteiro do que vamos falar, destacando o problema, a solução e o impacto.
-   **Meta:** Ter a primeira versão do código funcional e a estrutura da apresentação pronta.

### 4. Teste, Validação e Ensaio


A fase final é para garantir que tudo está funcionando e que nossa apresentação está afiada.

-   **Atividades:**
    -   Testar o código com os exemplos que definimos na Etapa 2.
    -   Validar se os resultados estão corretos.
    -   Fazer uma passagem rápida do pitch, garantindo que a explicação está clara e dentro do tempo.
-   **Meta:** Estar com a solução validada e o time confiante para a apresentação oficial!

---

##  Guia Rápido de Python (Nossas Ferramentas)

Um lembrete rápido das estruturas que provavelmente usaremos, com base nas diretrizes da dinâmica.

### Dicionários

Perfeitos para representar entidades com várias características (um candidato, um produto, etc.).

```python
# Exemplo de um candidato
candidato = {
    'nome': 'Ana',
    'habilidades': ['Python', 'Git'],
    'experiencia_meses': 8
}

# Acessando um valor
print(candidato['nome']) # Saída: Ana
```

### Listas

Ótimas para agrupar vários itens, como uma lista de candidatos ou de habilidades.

```python
habilidades_necessarias = ['Python', 'Git']
habilidades_candidato = ['Python', 'SQL', 'Git']

# Verificando se um item existe na lista
if 'Python' in habilidades_candidato:
    print("O candidato sabe Python!")
```

### Estruturas Condicionais (if/elif/else)

O coração da IA Simbólica! É aqui que nossas regras de negócio se transformam em código.

```python
# Exemplo de regra
score = 750
possui_restricao = False

if score > 700 and not possui_restricao:
    print("Aprovado")
elif score > 500:
    print("Análise manual")
else:
    print("Recusado")
```

### Laço de Repetição (for)

Essencial para processar uma lista de itens, aplicando nossa lógica a cada um deles.

```python
lista_de_candidatos = [candidato1, candidato2, candidato3]

for candidato in lista_de_candidatos:
    # Aplica a lógica de classificação para cada candidato aqui
    print(f"Analisando {candidato['nome']}...")
```

### Lendo um Arquivo CSV para uma Lista de Dicionários

Caso os dados venham em um arquivo (ex: `dados.csv`), podemos usar o módulo `csv` do Python para convertê-lo diretamente para o formato que precisamos. Assim, o resto da nossa lógica não precisa mudar.

**Exemplo de arquivo `dados.csv`:**
```csv
nome,habilidade,nivel
Ana,Python,Avançado
Bia,SQL,Intermediário
Carlos,Git,Iniciante
```

**Código Python:**
```python
import csv # Módulo nativo do Python

# Lista vazia para guardar nossos dicionários
dados_processados = []

with open('dados.csv', mode='r', encoding='utf-8') as arquivo:
    # DictReader transforma cada linha do CSV em um dicionário
    leitor_csv = csv.DictReader(arquivo) 
    
    for linha in leitor_csv:
        dados_processados.append(linha)

print(dados_processados)
```

**Saída Esperada do Código:**
```
[
    {'nome': 'Ana', 'habilidade': 'Python', 'nivel': 'Avançado'},
    {'nome': 'Bia', 'habilidade': 'SQL', 'nivel': 'Intermediário'},
    {'nome': 'Carlos', 'habilidade': 'Git', 'nivel': 'Iniciante'}
]
```

### Formatando a Saída de Dicionários e Listas (Pretty Print)

Quando temos estruturas complexas (como a lista de dicionários acima), usar `print()` pode gerar uma saída em uma única linha, difícil de ler. Para visualizar os dados de forma mais clara durante o desenvolvimento, podemos formatá-los.

**O jeito mais prático é usar o módulo `json`:**

```python
import json # Módulo nativo do Python

dados = [
    {'nome': 'Ana', 'habilidade': 'Python', 'nivel': 'Avançado'},
    {'nome': 'Bia', 'habilidade': 'SQL', 'nivel': 'Intermediário'},
    {'nome': 'Carlos', 'habilidade': 'Git', 'nivel': 'Iniciante'}
]

# Usamos json.dumps para formatar com indentação de 4 espaços
# O "ensure_ascii=False" ajuda a imprimir acentos corretamente
print(json.dumps(dados, indent=4, ensure_ascii=False))
```

**Saída Formatada (muito mais legível!):**
```json
[
    {
        "nome": "Ana",
        "habilidade": "Python",
        "nivel": "Avançado"
    },
    {
        "nome": "Bia",
        "habilidade": "SQL",
        "nivel": "Intermediário"
    },
    {
        "nome": "Carlos",
        "habilidade": "Git",
        "nivel": "Iniciante"
    }
]
```
 ### Formatando com tabela (opcional)

```python
 from collections import Counter

# (Opcional) mapa de cores (remova se não quiser)
CORES = {
    "VIP": "\033[92m",
    "ATIVO": "\033[94m",
    "INATIVO": "\033[90m",
    "RISCO": "\033[91m",
    "_reset": "\033[0m",
}

def colorizar(segmento):
    return f"{CORES.get(segmento, '')}{segmento}{CORES['_reset'] if segmento in CORES else ''}"

resultados = []

header = f"{'ID':<6}{'Compras':<10}{'Gasto(R$)':<12}{'Dias Ult.':<10}{'Segmento':<15}"
print(header)
print("-" * len(header))

for c in clientes:
    segmento = segmenta(c['total_compras'], c['valor_total_gasto'], c['dias_ultima_compra'])
    resultados.append({**c, 'segmento': segmento})
    print(
        f"{c['id_cliente']:<6}"
        f"{c['total_compras']:<10}"
        f"{c['valor_total_gasto']:<12.2f}"
        f"{c['dias_ultima_compra']:<10}"
        f"{colorizar(segmento):<15}"
    )

# Resumo
contagem = Counter(r['segmento'] for r in resultados)
print("\nResumo por segmento:")
for seg, qtd in contagem.items():
    print(f"- {seg}: {qtd}")

# Top gasto por segmento
print("\nTop gasto por segmento:")
for seg in contagem:
    grupo = [r for r in resultados if r['segmento'] == seg]
    top = max(grupo, key=lambda x: x['valor_total_gasto'])
    print(f"- {seg}: ID {top['id_cliente']} (R$ {top['valor_total_gasto']:.2f})")
``` 


```python
for c in clientes:
    segmento = segmenta(c['total_compras'], c['valor_total_gasto'], c['dias_ultima_compra'])
    print(f"Cliente {c['id_cliente']} | Compras={c['total_compras']} | Gasto=R${c['valor_total_gasto']:.2f} | Dias Última={c['dias_ultima_compra']} -> Segmento: {segmento}")
```