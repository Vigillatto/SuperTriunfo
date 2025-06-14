#include <stdio.h>

struct Carta {
    char codigo[4]; // Ex: A01
    char nomeCidade[50];
    unsigned long int populacao; 
    float area;
    float pib;
    int pontosTuristicos;
    float densidadePopulacional;
    float pibPerCapita;
    float superPoder;
};

int main() {
    struct Carta carta1, carta2;

    // Entrada dos dados - CARTA 1
    printf("Cadastro da Carta 1\n");
    printf("Codigo (ex: A01): ");
    scanf("%s", carta1.codigo);
    printf("Nome da cidade: ");
    scanf(" %[^\n]", carta1.nomeCidade);
    printf("Populacao: ");
    scanf("%lu", &carta1.populacao);
    printf("Area (km²): ");
    scanf("%f", &carta1.area);
    printf("PIB (em bilhoes): ");
    scanf("%f", &carta1.pib);
    printf("Numero de pontos turisticos: ");
    scanf("%d", &carta1.pontosTuristicos);

    // Calculos da carta 1
    carta1.densidadePopulacional = carta1.populacao / carta1.area;
    carta1.pibPerCapita = carta1.pib / carta1.populacao;
    carta1.superPoder = carta1.populacao + carta1.area + carta1.pib +
                        carta1.pontosTuristicos + carta1.pibPerCapita +
                        (1.0 / carta1.densidadePopulacional);

    // Entrada dos dados - CARTA 2
    printf("\nCadastro da Carta 2\n");
    printf("Codigo (ex: B02): ");
    scanf("%s", carta2.codigo);
    printf("Nome da cidade: ");
    scanf(" %[^\n]", carta2.nomeCidade);
    printf("Populacao: ");
    scanf("%lu", &carta2.populacao);
    printf("Area (km²): ");
    scanf("%f", &carta2.area);
    printf("PIB (em bilhoes): ");
    scanf("%f", &carta2.pib);
    printf("Numero de pontos turisticos: ");
    scanf("%d", &carta2.pontosTuristicos);

    // Calculos da carta 2
    carta2.densidadePopulacional = carta2.populacao / carta2.area;
    carta2.pibPerCapita = carta2.pib / carta2.populacao;
    carta2.superPoder = carta2.populacao + carta2.area + carta2.pib +
                        carta2.pontosTuristicos + carta2.pibPerCapita +
                        (1.0 / carta2.densidadePopulacional);

    // Exibicao dos dados - CARTA 1
    printf("\n--- Carta 1 ---\n");
    printf("Codigo: %s\n", carta1.codigo);
    printf("Cidade: %s\n", carta1.nomeCidade);
    printf("Populacao: %lu\n", carta1.populacao);
    printf("Area: %.2f km2\n", carta1.area);
    printf("PIB: %.2f bilhoes\n", carta1.pib);
    printf("Pontos Turisticos: %d\n", carta1.pontosTuristicos);
    printf("Densidade Populacional: %.2f hab/km2\n", carta1.densidadePopulacional);
    printf("PIB per Capita: %.6f\n", carta1.pibPerCapita);
    printf("Super Poder: %.6f\n", carta1.superPoder);

    // Exibicao dos dados - CARTA 2
    printf("\n--- Carta 2 ---\n");
    printf("Codigo: %s\n", carta2.codigo);
    printf("Cidade: %s\n", carta2.nomeCidade);
    printf("Populacao: %lu\n", carta2.populacao);
    printf("Area: %.2f km2\n", carta2.area);
    printf("PIB: %.2f bilhoes\n", carta2.pib);
    printf("Pontos Turisticos: %d\n", carta2.pontosTuristicos);
    printf("Densidade Populacional: %.2f hab/km2\n", carta2.densidadePopulacional);
    printf("PIB per Capita: %.6f\n", carta2.pibPerCapita);
    printf("Super Poder: %.6f\n", carta2.superPoder);

    // Comparacao das cartas
    printf("\n--- Comparacao ---\n");
    printf("Populacao: %d\n", carta1.populacao > carta2.populacao); // 1 se carta1 vence
    printf("Area: %d\n", carta1.area > carta2.area);
    printf("PIB: %d\n", carta1.pib > carta2.pib);
    printf("Pontos Turisticos: %d\n", carta1.pontosTuristicos > carta2.pontosTuristicos);
    printf("Densidade Populacional (vence menor): %d\n", carta1.densidadePopulacional < carta2.densidadePopulacional);
    printf("PIB per Capita: %d\n", carta1.pibPerCapita > carta2.pibPerCapita);
    printf("Super Poder: %d\n", carta1.superPoder > carta2.superPoder);

    return 0;
}
