# Atividade – Execução de teste com xUnit (UC 15 · Testes de Back-End)

Projeto xUnit que testa a classe `IMC` (cálculo e classificação do Índice de Massa Corporal).

## Estrutura
```
atividade_imc_xunit/
├── atividade_imc_xunit.csproj
├── GlobalUsings.cs
├── imc.cs            # classe IMC (Calcular_IMC e Classificar_IMC)
└── UnitTest1.cs      # 1 [Fact] + 1 [Theory] com 6 casos
```

## Como executar
```bash
cd atividade_imc_xunit
dotnet build
dotnet test
```

## Resultado esperado
Entrada dos testes: peso = 80 kg, altura = 1,60 m → IMC = 31,25 → **Obesidade Grau I**.

| Teste | Resultado |
|---|---|
| `Teste_Calculo_IMC` (31,25) | Aprovado |
| `Teste_Categoria_IMC("Obesidade Grau I")` | Aprovado |
| `Teste_Categoria_IMC("Abaixo do peso")` | Falha |
| `Teste_Categoria_IMC("Peso normal")` | Falha |
| `Teste_Categoria_IMC("Sobrepeso")` | Falha |
| `Teste_Categoria_IMC("Obesidade Grau II")` | Falha |
| `Teste_Categoria_IMC("Obesidade Grau III")` | Falha |

Resumo: **Total 7 · Aprovado 2 · Com falha 5**. As falhas são esperadas: o `[Theory]` usa sempre os mesmos dados de entrada, então só a categoria correta passa.

## Ajustes feitos nos arquivos originais
- `imc.cs`: o `namespace` estava vazio; passou a ser `namespace atividade_imc_xunit`.
- `UnitTest1.cs`: os métodos foram colocados dentro de `namespace atividade_imc_xunit; public class UnitTest1`.
