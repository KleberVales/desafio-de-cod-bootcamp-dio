# desafio-de-cod-bootcamp-dio

## Descrição
Você foi contratado para desenvolver um sistema que calcule a velocidade média de conexão de internet de um cliente durante um período. O sistema deve ler os registros recebidos como entrada, processar os dados e calcular a velocidade média de conexão em megabits por segundo (Mbps) ao longo do turno.

## Entrada
A entrada é uma string contendo uma lista de valores representando a velocidade de conexão em megabits por segundo (Mbps), separados por vírgulas.

## Saída
A saída do programa deve ser a velocidade média de conexão em Mbps. O sistema deve somar todos os valores da lista de entrada, calcular a média dividindo o total pelo número de registros, e exibir o resultado.

## Exemplos
A tabela abaixo apresenta exemplos com alguns dados de entrada e suas respectivas saídas esperadas. Certifique-se de testar seu programa com esses exemplos e com outros casos possíveis.

```
import java.util.Scanner;

public class Main {

    // Função para calcular a velocidade média de conexão de internet
    public static double calcularVelocidadeMedia(String[] velocidades) {
        int total = 0;

        // Percorre cada velocidade no array
        for (String velocidadeStr : velocidades) {
            // Remove espaços em branco e converte para inteiro
            int velocidade = Integer.parseInt(velocidadeStr.trim());
            total += velocidade;
        }

        // Calcula a média
        double media = (double) total / velocidades.length;
        return media;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Solicitando ao usuário a lista de velocidades de conexão registradas a cada hora
        String input = scanner.nextLine();

        // Convertendo a entrada em uma lista de strings
        String[] velocidades = input.split(",");

        // Calculando a velocidade média de conexão
        double velocidadeMedia = calcularVelocidadeMedia(velocidades);

        // Exibindo a velocidade média de conexão (convertendo para inteiro)
        System.out.println((int)velocidadeMedia + " Mbps");

        scanner.close();
    }
}
```
