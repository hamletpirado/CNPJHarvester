# CNPJHarvester

# CNPJHarvester

## Descrição
CNPJHarvester é uma ferramenta automatizada para extração e enriquecimento de dados de CNPJs a partir de planilhas Excel. O aplicativo localiza o arquivo Excel mais recente em uma pasta específica, extrai os CNPJs, consulta a API da ReceitaWS para obter informações detalhadas sobre cada empresa e salva os resultados em um arquivo CSV estruturado.

## Principais Funcionalidades
- Localização automática do arquivo Excel mais recente na pasta especificada
- Extração e validação de CNPJs da coluna "Nr. CNPJ/CPF"
- Consulta à API da ReceitaWS para obtenção de dados detalhados das empresas
- Tratamento de limitações de taxa (rate limiting) na API
- Geração de arquivo CSV estruturado com informações relevantes das empresas
- Suporte a até 1000 CNPJs por execução

## Dados Coletados
Para cada CNPJ, o sistema coleta:
- Nome da empresa
- UF e município
- Endereço completo (logradouro, número, bairro, CEP)
- Regime tributário (natureza jurídica)
- Status de optante pelo Simples Nacional
- Status de optante pelo MEI

## Requisitos
- Python 3.6+
- Bibliotecas: pandas, requests

## Como Usar
1. Modifique a variável `pasta_Nome_da_sua_pasta` no código para substituir "Nome_da_sua_pasta" pelo nome da pasta onde seus arquivos Excel estão armazenados.
2. Execute o script.
3. O resultado será salvo como 'D_F_EMPRESAS.csv' na mesma pasta.

## Limitações
- A API da ReceitaWS possui limites de consultas. O script implementa espera entre requisições para mitigar isso.
- Apenas os primeiros 1000 CNPJs serão processados em cada execução.
