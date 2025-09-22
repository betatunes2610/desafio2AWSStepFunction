# desafio2AWSStepFunction
Descrição

Este projeto demonstra a utilização do AWS Step Functions para orquestrar workflows de microsserviços na AWS. O objetivo é criar uma automatização não muito complexa com o intuito de aprender colocando a mão na masssa .

O AWS Step Function pode ser adaptado para vários cenários.

Utilizei a Validação e processamento de arquivos em um bucket S3.

O fluxo de execução do Step Functions no projeto é:

Start Execution

O workflow é disparado por um evento (ex: upload de arquivo no S3).

Choice State

Se o arquivo for do tipo image → Process Image

Se o arquivo for do tipo document → Process Document

Process File

Lambda Process Document pega o arquivo de um bucket e joga em outro bucket.

Já o Lambda Process Image pegar o arquivo de imagem, abre esse arquivo e redimensiona.

End Execution

Serviços Utilizados

AWS Step Functions – Orquestração do fluxo.

AWS Lambda – Execução de funções de validação e processamento.

Amazon S3 – Armazenamento dos arquivos.

Choice State – Funciona como um if/else dentro do Step Functions. Ele permite que a execução siga caminhos diferentes com base em condições avaliadas a partir do input da máquina de estado.

IAM Roles – Permissões para execução das funções.


Esse desafio foi interessante, pois deparei com vários erros durante a construção e a execução, desde roles que nao estam autorizadas para determinado serviço, ou ate buckets que nao tinha permissao para a execução
de Put ou get e até mesmo na questao de módulos python (pillow - que é utilizado para manipulação de imagens) ainda nao compatíveis com a versao python 3.13 e alguns outros erros.

👉 Esse README pode servir tanto como guia de estudo quanto documentação de um repositório de exemplos práticos.
