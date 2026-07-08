# Campo Magnético no Centro de um Quadrado

Resolução detalhada do problema

---

## Enunciado

Na Fig. 29.34, quatro fios longos e retilíneos são perpendiculares ao
papel, e suas seções retas formam um quadrado de lado **a = 20 cm**.

- As correntes são **para fora do papel** nos fios **1** e **4**
- As correntes são **para dentro do papel** nos fios **2** e **3**
- Todos os fios conduzem uma corrente de **I = 20 A**

**Pergunta:** na notação dos vetores unitários, qual é o campo magnético
no centro do quadrado?

---

## Geometria do problema

Posicionando os eixos com origem no fio 4 (canto inferior esquerdo):

| Fio | Posição      | Corrente         |
|-----|--------------|------------------|
| 1   | (0, a)       | Saindo do papel  |
| 2   | (a, a)       | Entrando no papel|
| 3   | (a, 0)       | Entrando no papel|
| 4   | (0, 0)       | Saindo do papel  |

O centro do quadrado fica em **(a/2, a/2)**, no cruzamento das diagonais.

### Distância de cada fio ao centro

Como o centro é o ponto médio das diagonais do quadrado:

```
r = a / √2
```

Essa distância é **igual para os quatro fios** — é o que torna o problema
simétrico e mais simples de resolver.

---

## Passo a passo da resolução

### 1. Campo de um fio infinito

O módulo do campo magnético gerado por um fio longo, a uma distância `r`,
é dado pela Lei de Ampère:

```
B_fio = μ₀ I / (2π r)
```

Como `r` é igual para todos os fios, **todos os quatro campos individuais
têm o mesmo módulo**.

### 2. Direção de cada campo (regra da mão direita)

A direção do campo de cada fio é sempre **perpendicular** à reta que liga
o fio ao centro (que aqui é uma diagonal a 45°). Usando a regra da mão
direita (polegar no sentido da corrente, dedos indicando o giro de B):

| Fio | Sentido da corrente  | Direção do campo no centro |
|-----|-----------------------|------------------------------|
| 1   | Saindo do papel       | ↗ (nordeste)                 |
| 2   | Entrando no papel     | ↖ (noroeste)                 |
| 3   | Entrando no papel     | ↗ (nordeste)                 |
| 4   | Saindo do papel       | ↖ (noroeste)                 |

### 3. Decomposição em x e y

Cada vetor a 45° tem componentes **x** e **y** de mesmo módulo:

```
componente = B_fio / √2
```

Somando os quatro vetores:

- **Eixo x:** as contribuições se cancelam totalmente → `Bx = 0`
- **Eixo y:** as quatro contribuições se somam no mesmo sentido:

```
By = 4 × (B_fio / √2)
```

> O cancelamento em x e o reforço em y não são coincidência — vêm
> diretamente da simetria do arranjo (correntes alternadas entrando e
> saindo em vértices opostos).

### 4. Simplificação algébrica

Substituindo `B_fio = μ₀I / (2πr)` e `r = a/√2` na expressão de `By`,
os fatores de `√2` se cancelam, resultando em uma fórmula final compacta:

```
B = (2 μ₀ I) / (π a)
```

---

## Cálculo numérico

Dados:
- I = 20 A
- a = 0,20 m
- μ₀ = 4π × 10⁻⁷ T·m/A

```
B_fio = (4π×10⁻⁷)(20) / (2π × 0,20/√2) ≈ 2,83 × 10⁻⁵ T

By = 4 × (2,83×10⁻⁵ / √2) ≈ 8,0 × 10⁻⁵ T
```

---

## Resultado final

```
Bx = 0
By = 8,0 × 10⁻⁵ T
```

O campo magnético resultante no centro do quadrado tem módulo
**8,0 × 10⁻⁵ T (80 μT)**, apontando inteiramente na direção **+y**.

Em notação de vetores unitários:

```
B = 8,0 × 10⁻⁵ ĵ  T
```

---

## Conceitos-chave

- Campo magnético gerado por fio retilíneo infinito (Lei de Ampère)
- Regra da mão direita para determinar direção/sentido de **B**
- Decomposição vetorial em componentes x e y
- Uso de simetria para simplificar somas vetoriais

---
