title: Método de Newton
code: ACT001
---
![Newton](/images/Ativ9-images.jpg)

    function newtonInterpolation(x, y, targetX) {
        const n = x.length;
        let dividedDifferences = Array(n).fill().map(() => Array(n).fill(0));
        for (let i = 0; i < n; i++) {
            dividedDifferences[i][0] = y[i];
        }
        for (let j = 1; j < n; j++) {
            for (let i = 0; i < n - j; i++) {
                dividedDifferences[i][j] = (dividedDifferences[i + 1][j - 1] - dividedDifferences[i][j - 1]) / (x[i + j] - x[i]);
            }
        }
        let newtonPol = dividedDifferences[0][0];
        let productTerms = 1;
        for (let j = 1; j < n; j++) {
            productTerms *= (targetX - x[j - 1]);
            newtonPol += dividedDifferences[0][j] * productTerms;
        }
        return newtonPol;

## Descrição
O método de interpolação de Newton é uma técnica usada para encontrar um polinômio que passa por um conjunto de pontos dados. É uma forma eficiente de interpolação polinomial que se baseia nas diferenças divididas. 
