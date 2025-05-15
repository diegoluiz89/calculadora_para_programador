# calculadora_para_programador

#include <iostream>
#include <bitset>
#include <iomanip>

using namespace std;

void exibirMenu() {
    cout << "\n=== Calculadora para Programadores ===\n";
    cout << "1. Soma (+)\n";
    cout << "2. Subtracao (-)\n";
    cout << "3. Multiplicacao (*)\n";
    cout << "4. Divisao (/)\n";
    cout << "5. AND (&)\n";
    cout << "6. OR (|)\n";
    cout << "7. XOR (^)\n";
    cout << "8. NOT (~)\n";
    cout << "9. Shift Left (<<)\n";
    cout << "10. Shift Right (>>)\n";
    cout << "11. Converter para Binario\n";
    cout << "12. Converter para Hexadecimal\n";
    cout << "0. Sair\n";
    cout << "Escolha uma opcao: ";
}

void converterParaBinario(int num) {
    cout << "Binario: " << bitset<32>(num) << endl;
}

void converterParaHexadecimal(int num) {
    cout << "Hexadecimal: 0x" << hex << uppercase << num << dec << endl;
}

int main() {
    int opcao;
    int a, b;

    do {
        exibirMenu();
        cin >> opcao;

        switch (opcao) {
            case 1:
                cout << "Digite dois numeros: ";
                cin >> a >> b;
                cout << "Resultado: " << a + b << endl;
                break;
            case 2:
                cout << "Digite dois numeros: ";
                cin >> a >> b;
                cout << "Resultado: " << a - b << endl;
                break;
            case 3:
                cout << "Digite dois numeros: ";
                cin >> a >> b;
                cout << "Resultado: " << a * b << endl;
                break;
            case 4:
                cout << "Digite dois numeros: ";
                cin >> a >> b;
                if (b != 0)
                    cout << "Resultado: " << a / b << endl;
                else
                    cout << "Erro: Divisao por zero!" << endl;
                break;
            case 5:
                cout << "Digite dois numeros: ";
                cin >> a >> b;
                cout << "Resultado: " << (a & b) << endl;
                break;
            case 6:
                cout << "Digite dois numeros: ";
                cin >> a >> b;
                cout << "Resultado: " << (a | b) << endl;
                break;
            case 7:
                cout << "Digite dois numeros: ";
                cin >> a >> b;
                cout << "Resultado: " << (a ^ b) << endl;
                break;
            case 8:
                cout << "Digite um numero: ";
                cin >> a;
                cout << "Resultado: " << (~a) << endl;
                break;
            case 9:
                cout << "Digite o numero e a quantidade de bits para shift left: ";
                cin >> a >> b;
                cout << "Resultado: " << (a << b) << endl;
                break;
            case 10:
                cout << "Digite o numero e a quantidade de bits para shift right: ";
                cin >> a >> b;
                cout << "Resultado: " << (a >> b) << endl;
                break;
            case 11:
                cout << "Digite um numero: ";
                cin >> a;
                converterParaBinario(a);
                break;
            case 12:
                cout << "Digite um numero: ";
                cin >> a;
                converterParaHexadecimal(a);
                break;
            case 0:
                cout << "Saindo...\n";
                break;
            default:
                cout << "Opcao invalida!\n";
        }

    } while (opcao != 0);

    return 0;
}
