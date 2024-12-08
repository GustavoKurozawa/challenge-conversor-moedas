import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;
import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;
import java.util.Map;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        ConsultaCambio consulta = new ConsultaCambio();
        List<String> historico = new ArrayList<>();

        try {
            while(true){

                System.out.println("--------MENU--------");
                System.out.println("Opções:");
                System.out.println("1 - Converter um valor\n2 - Histórico de Conversões\n3 - Sair");

                try {
                    int opcao = Integer.parseInt(scanner.nextLine()); // Tenta converter a entrada para um int

                    if (opcao == 1){

                        System.out.println("Digite o código da moeda base:");
                        String moedaBase = scanner.nextLine().toUpperCase();

                        // Obter as taxas de câmbio com a moeda base fornecida
                        Map<String, Double> taxas;
                        try {
                            taxas = consulta.getConversionRates(moedaBase);
                        } catch (Exception e) {
                            System.out.println("Erro ao obter as taxas para a moeda base. Tente novamente.");
                            continue;
                        }

                        System.out.println("Digite o código da moeda para conversão: ");
                        String moedaAlvo = scanner.nextLine().toUpperCase();

                        if (!taxas.containsKey(moedaAlvo)) {
                            System.out.println("Moeda de destino não encontrada! Tente novamente.");
                            continue;
                        }

                        // Pergunta o valor a ser convertido
                        System.out.println("Digite o valor a ser convertido: ");
                        double valor = 0;
                        try {
                            valor = Double.parseDouble(scanner.nextLine());
                        } catch (NumberFormatException e) {
                            System.out.println("Valor inválido! Por favor, digite um número válido.");
                            continue;
                        }

                        // Realizar a conversão
                        double taxa = taxas.get(moedaAlvo);
                        double convertido = valor * taxa;

                        // Exibir o resultado
                        System.out.printf("Valor convertido: %.2f %s%n", convertido, moedaAlvo);

                        // Adicionar ao histórico
                        String dataHora = LocalDateTime.now().format(DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm:ss"));
                        historico.add(String.format("%s - %.2f %s para %.2f %s", dataHora, valor, moedaBase, convertido, moedaAlvo));

                    }else if(opcao == 2){
                        System.out.println("\nHistórico de conversões:");
                        historico.forEach(System.out::println);
                    }else{
                        System.out.println("Finalizando o programa");
                        break;
                    }

                } catch (NumberFormatException e) {
                    System.out.println("Entrada inválida. Por favor, digite um número inteiro.");
                    continue;
                }

            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
