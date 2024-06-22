title: Método de Lagrange
code: ACT001
---
![Lagrange](/images/Ativ8-images.jpg)

    function lagrangeInterpolation(x, y, targetX) {
        const n = x.length;
        let lagrangePol = 0;
        for (let i = 0; i < n; i++) {
            let term = y[i];
            for (let j = 0; j < n; j++) {
                if (j !== i) {
                    term *= (targetX - x[j]) / (x[i] - x[j]);
                }
            }
            lagrangePol += term;
        }
        return lagrangePol;
    }

## Descrição
O método de interpolação de Lagrange é uma técnica matemática usada para encontrar um polinômio que passa exatamente por um conjunto de pontos dados. Este método é particularmente útil na análise numérica e na computação para interpolar funções discretas. 