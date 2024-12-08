# Currency Converter API

Um projeto em Java que realiza conversões de valores entre diferentes moedas, utilizando uma API de taxas de câmbio. Este programa permite:

- Informar a moeda base.
- Informar a moeda de destino.
- Converter valores de forma dinâmica.
- Gerar um histórico das conversões realizadas com data e hora.

## ⚙️ Funcionalidades

1. **Seleção de Moeda Base**: 
   - O usuário pode escolher a moeda inicial para conversão.
2. **Validação da Moeda Alvo**: 
   - Verifica se a moeda de destino é válida.
3. **Conversão de Valores**:
   - Realiza cálculos com base nas taxas retornadas pela API.
4. **Histórico de Conversões**:
   - Mantém um registro das operações realizadas, incluindo data e hora.

---

## 🚀 Tecnologias Utilizadas

- **Java 17**: Linguagem de programação principal.
- **HttpClient**: Para realizar requisições HTTP.
- **Gson**: Biblioteca para manipulação e deserialização de JSON.
- **API de Conversão de Moedas**: [Exchangerate-API](https://www.exchangerate-api.com).

---

💡 Dificuldades Enfrentadas e Soluções
1. Deserialização do JSON
Desafio: Identificar como extrair as taxas de câmbio (conversion_rates) do JSON retornado pela API.
Solução: Utilizei a biblioteca Gson para deserializar os dados e converter os valores em um Map<String, Double> para facilitar a manipulação.
2. Validação da Entrada do Usuário
Desafio: Tratar entradas inválidas, como letras ao invés de números.
Solução: Usei try-catch para capturar exceções e solicitei novamente a entrada do usuário até que fosse válida.
3. Mudança Dinâmica da Moeda Base
Desafio: Permitir que o usuário informe a moeda base dinamicamente e atualize a URL da API.
Solução: Modifiquei a URL da API para incluir a moeda base escolhida e utilizei um método separado na classe CurrencyApiService para gerenciar isso.
4. Histórico de Conversões
Desafio: Gerar um histórico legível e bem formatado das conversões realizadas.
Solução: Implementei uma lista para armazenar os registros com data e hora usando a classe LocalDateTime e formatei as entradas para uma exibição clara.

🧑‍💻 Autor
Desenvolvido por Gustavo Kurozawa. Se tiver dúvidas ou sugestões, sinta-se à vontade para entrar em contato! 😊
