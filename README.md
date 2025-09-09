# Analisador de Variação de Preços

📌 **Descrição**  
Projeto em C que permite registrar preços antigos e novos de produtos, calcular a variação percentual e indicar se houve aumento, aumento abusivo, queda ou estabilidade. Ideal para analisar mudanças de preço de forma rápida.

---

## 🛠 Tecnologias
- Linguagem C  
- Console/Terminal  
- Estruturas de dados básicas (variáveis, arrays simples)  
- Laços de repetição e condicionais  

---

## ⚙ Funcionalidades
- Recebe o **nome** e os **preços antigo e novo** de 3 produtos  
- Calcula a **variação percentual** do preço de cada produto  
- Classifica a situação do produto:  
  - **Aumento Abusivo** (variação > 10%)  
  - **Aumento** (variação > 0%)  
  - **Queda** (variação < 0%)  
  - **Estável** (variação = 0%)  
- Exibe um **resumo detalhado** de cada produto  

---

## 💻 Código Fonte

```c
#include <stdio.h>

// Função para exibir o resumo do produto
void resumo_produto(char nome[], float antigo, float novo, float variacao) {
    printf("Produto: %s\nPreco Anterior: %.2f \nPreco Atual: %.2f \nVariacao: %.2f%% \n", nome, antigo, novo, variacao);
    if (variacao > 10) {
        printf("Situacao: AUMENTO ABUSIVO\n\n");
    } else if (variacao > 0) {
        printf("Situacao: AUMENTO\n\n");
    } else if (variacao < 0) {
        printf("Situacao: QUEDA\n\n");
    } else {
        printf("Situacao: ESTAVEL\n\n");
    }
}

int main() {
    char item1[50], item2[50], item3[50];
    float preco1_antigo, preco1_novo, preco2_antigo, preco2_novo, preco3_antigo, preco3_novo;
    float variacao1, variacao2, variacao3;

    printf("Digite o nome do item 1: ");
    scanf("%s", item1);
    printf("Digite o preco antigo do item 1: ");
    scanf("%f", &preco1_antigo);
    printf("Digite o novo preco do item 1: ");
    scanf("%f", &preco1_novo);

    variacao1 = ((preco1_novo - preco1_antigo) / preco1_antigo) * 100;

    printf("Digite o nome do item 2: ");
    scanf("%s", item2);
    printf("Digite o preco antigo do item 2: ");
    scanf("%f", &preco2_antigo);
    printf("Digite o novo preco do item 2: ");
    scanf("%f", &preco2_novo);

    variacao2 = ((preco2_novo - preco2_antigo) / preco2_antigo) * 100;

    printf("Digite o nome do item 3: ");
    scanf("%s", item3);
    printf("Digite o preco antigo do item 3: ");
    scanf("%f", &preco3_antigo);
    printf("Digite o novo preco do item 3: ");
    scanf("%f", &preco3_novo);

    variacao3 = ((preco3_novo - preco3_antigo) / preco3_antigo) * 100;

    printf("\nResumo dos produtos:\n");
    resumo_produto(item1, preco1_antigo, preco1_novo, variacao1);
    resumo_produto(item2, preco2_antigo, preco2_novo, variacao2);
    resumo_produto(item3, preco3_antigo, preco3_novo, variacao3);

    return 0;
}
```
### 📌 Exemplo de Saída

Resumo dos produtos:
Produto: Arroz
Preco Anterior: 20.00
Preco Atual: 25.00
Variacao: 25.00%
Situacao: AUMENTO ABUSIVO

Produto: Celular
Preco Anterior: 20.00
Preco Atual: 20.00
Variacao: 00.00%
Situacao: ESTAVEL

Produto: Feijao
Preco Anterior: 20.00
Preco Atual: 10.00
Variacao: -50.00%
Situacao: QUEDA


