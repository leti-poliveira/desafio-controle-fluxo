# Desafio Controle de Fluxo

Este é um projeto desenvolvido como parte da trilha Java Básico do DIO (Digital Innovation One). O desafio consiste em criar um programa em Java que recebe dois parâmetros via terminal e realiza uma contagem e impressão dos números incrementados, com base nos parâmetros fornecidos. Além disso, o programa deve lançar uma exceção customizada se o segundo parâmetro for menor ou igual ao primeiro.

## Instruções

1. Crie o projeto `DesafioControleFluxo`.
2. Dentro do projeto, crie a classe `Contador.java` para realizar toda a codificação do nosso programa.
3. Dentro do projeto, crie a classe `ParametrosInvalidosException` que representará a exceção de negócio no sistema.
4. Siga as instruções abaixo para o código do programa:

```java
import java.util.Scanner;

public class Contador {
    public static void main(String[] args) {
        Scanner terminal = new Scanner(System.in);
        System.out.println("Digite o primeiro parâmetro");
        int parametroUm = terminal.nextInt();
        System.out.println("Digite o segundo parâmetro");
        int parametroDois = terminal.nextInt();
        
        try {
            contar(parametroUm, parametroDois);
        } catch (ParametrosInvalidosException e) {
            System.out.println("O segundo parâmetro deve ser maior que o primeiro");
        }
        
    }

    static void contar(int parametroUm, int parametroDois) throws ParametrosInvalidosException {
        if (parametroUm >= parametroDois) {
            throw new ParametrosInvalidosException("O segundo parâmetro deve ser maior que o primeiro");
        } else {
            int contagem = parametroDois - parametroUm;
            for (int i = 1; i <= contagem; i++) {
                System.out.println("Imprimindo o número " + (parametroUm + i));
            }
        }
    }
}

class ParametrosInvalidosException extends Exception {
    public ParametrosInvalidosException(String message) {
        super(message);
    }
}
