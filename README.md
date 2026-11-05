# faculdade_programacao-1_caixeiro-viajante

Estudo formal e comparativo de algoritmos para resolução do clássico **Problema do Caixeiro Viajante (Traveling Salesperson Problem - TSP)**, contrapondo **Busca Exaustiva / Força Bruta ($O(V!)$)** contra a meta-heurística **GRASP (Greedy Randomized Adaptive Search Procedure)** com refinamento local **2-opt**.

Desenvolvido no âmbito da disciplina de **Programação I / Análise de Algoritmos** do Bacharelado em Ciência da Computação na Universidade Federal do Pará (UFPA).

---

## 🔬 Algoritmos e Implementação

1. **Força Bruta ($O(V!)$):**
   - Algoritmo recursivo de permutação combinatorial avaliando todos os ciclos hamiltonianos possíveis e calculando a distância euclidiana acumulada de retorno ao ponto de origem.
2. **Heurística Construtiva Gulosa:**
   - Construção rápida de rota inicial em $O(V^2)$ selecionando sequencialmente a cidade mais próxima ainda não visitada.
3. **Busca Local 2-opt:**
   - Procedimento de otimização iterativa que testa reversões sistemáticas de arestas para desenlaçar cruzamentos de caminhos e alcançar um ótimo local eficiente.
4. **GRASP (Greedy Randomized Adaptive Search Procedure):**
   - Meta-heurística com randomização adaptativa na escolha do vértice inicial, construção gulosa e refinamento por busca local 2-opt.

---

## 📊 Bancada Experimental Instrumentada

| N° Cidades | Algoritmo | Distância Mínima Encontrada | Total de Iterações Computadas | Razão de Eficiência |
| :---: | :---: | :---: | :---: | :---: |
| **3 Cidades** | Força Bruta | 29 | **69** iterações | Base ótima |
| **3 Cidades** | GRASP (2 buscas, 3 largadas) | 29 | **160** iterações | Overhead inicial |
| **6 Cidades** | Força Bruta | 177 | **22.320** iterações | $O(V!)$ exponencial |
| **6 Cidades** | GRASP (2 buscas, 6 largadas) | 177 | **3.029** iterações | **7,3x menos iterações** |
| **9 Cidades** | Força Bruta | 204 | **21.591.360** iterações | Explosão combinatorial |
| **9 Cidades** | GRASP (2 buscas, 9 largadas) | 204 | **15.347** iterações | **1.406x menos iterações** |
| **12 Cidades** | Força Bruta | *Inviável* | *Crash por OOM (RAM)* | Esgotamento de memória |
| **12 Cidades** | GRASP (2 buscas, 12 largadas) | **295** | **47.931** iterações | **Convergência em segundos** |

---

## 📦 Como Executar

```bash
# 1. Clonar o repositório
git clone https://github.com/Julio-C-Oliveira/faculdade_programacao-1_caixeiro-viajante.git
cd faculdade_programacao-1_caixeiro-viajante

# 2. Configurar ambiente
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt

# 3. Iniciar Jupyter Notebook
jupyter notebook Caixeiro_Viajante.ipynb
```

---

## 📄 Licença
Distribuído sob a licença MIT. Veja `LICENSE` para mais detalhes.
