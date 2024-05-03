import java.util.Scanner;

public class Main {

    static int saldoConta = 2500;

    public static void main(String[] args) {

        String nomeCliente = "Gabriel Augusto do Vale Ribeiro";
        String contaCliente = "Conta Corrente";
        int saldoConta = 2500;
dadosCliente(nomeCliente,contaCliente,saldoConta);
operacao();

//teste classes
//saldoConta =  receberTransferencia(saldoConta);
//saldoConta =  tranferirValor(saldoConta);
//        System.out.println(saldoConta);


     }
    public static void dadosCliente(String a, String b, int c){
        Scanner leitura = new Scanner(System.in);

        String base =
                """
                 ***************************************
                 
                 Dados Inicial do Cliente:
                 
                 Nome: """+ a + """
                        
                 """ +
                 "Tipo de Conta:" + b + """
                         
                 """ +

                 "Saldo Inicial: "+ c +"""
                 
                 """ +

                 """
                   
                 ***************************************
              """;
        System.out.printf(base);

    }

    public static int receberTransferencia(int saldo){

        Scanner leitura = new Scanner(System.in);
        System.out.println("Informe o Valor que deseja Receber.");
        String t = leitura.nextLine();
        int q = Integer.parseInt(t);

        if (q > 0) {
            saldo = q + saldo;
        }
        else {
            System.out.println("Valor Invalido");
        }
// testando operação
       // System.out.print("Seu Saldo atual é:");
        //System.out.println(saldo);

        return saldo;
    }

    public static int tranferirValor(int transfSaldo){
        Scanner leitura = new Scanner(System.in);
        System.out.println("Informe o Valor que deseja Transferir.");
        String tr = leitura.nextLine();
        int qr = Integer.parseInt(tr);

        if (qr > 0) {
            if (transfSaldo >= qr){
            transfSaldo = transfSaldo - qr;
            }
            else {
                System.out.println("Saldo Insufuciente");
            }
        }
        else {
            System.out.println("Valor Invalido");
        }
    // testando operação
       // System.out.print("Seu Saldo atual é:");
       // System.out.println(transfSaldo);

        return transfSaldo;

    }

    public static void   operacao() {

        String dadosoperacao = """
                         
                Operações
                         
                1- Consultar de Saldos
                2- Receber Valor
                3- Transferir Valor
                4 Sair
                         
                 """;

        System.out.println(dadosoperacao);
        Scanner leitura = new Scanner(System.in);
        System.out.println("Digite a opção desejada:");
        String t = leitura.nextLine();
        int q = Integer.parseInt(t);

        if (q < 4 || q > 0) {
            if (q == 1) {

                System.out.print("Seu Saldo atual é:");
                System.out.println(saldoConta);
                operacao();

            }
            if (q == 2) {
                saldoConta = receberTransferencia(saldoConta);
                System.out.print("Seu Saldo atual é:");
                System.out.println(saldoConta);
                operacao();

            }
            if (q == 3) {
                saldoConta = tranferirValor(saldoConta);
                System.out.print("Seu Saldo atual é:");
                System.out.println(saldoConta);
                operacao();

            }
            if (q == 4) {
                     System.out.print("Feche o aplicativo para sair com segurança");
                        }
        }
    }
    }
