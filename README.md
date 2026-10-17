# Gerador-de-Senhas-experimental
Gerador de Senhas Seguras — Mini-projeto UFG/AKCIT
Mini-projeto educacional em Python desenvolvido com apoio de IA generativa. O programa gera senhas aleatórias com tamanho e categorias de caracteres configuráveis. A IA apoiou a criação do software; ela não é usada para gerar as senhas durante a execução.
Funcionalidades
- Senhas de 8 a 128 caracteres (padrão: 16).
- Opção de incluir/excluir minúsculas, maiúsculas, dígitos e símbolos.
- Pelo menos um caractere de cada categoria selecionada.
- Geração de 1 a 20 senhas por execução no terminal.
- Mensagens de erro para configurações inválidas.
- Sem banco de dados, conexão à internet ou armazenamento de senhas.
Executar no Google Colab (opção mais simples)
1. Entre em https://colab.research.google.com/ com sua conta Google.
2. Vá a Arquivo > Fazer upload de notebook.
3. Selecione GeradorSenhasUFG_Colab.ipynb.
4. Escolha Ambiente de execução > Executar tudo.
5. Observe as senhas geradas e os resultados dos testes e altere parâmetros nas células de demonstração.
O notebook é uma forma didática de executar a mesma lógica de geração de senhas. Para os 15 testes do repositório, utilize o comando Python indicado abaixo. Testes do notebook e do repositório podem ter contagens diferentes.

Executar localmente (Windows, macOS ou Linux)
Requisito: Python 3.10 ou superior. Não há dependências externas de execução.
python gerador_senhas.py
Para gerar 3 senhas de 20 caracteres sem símbolos:
python gerador_senhas.py --tamanho 20 --quantidade 3 --sem-simbolos
Para verificar todas as opções:
python gerador_senhas.py --help
Alternativa de instalação (opcional): pip install . cria o comando gerador-senhas. Esse passo pode baixar dependências de empacotamento (setuptools, wheel); não é necessário para rodar os exemplos acima.
Testes automatizados
No diretório raiz, execute:
python -m unittest discover -s tests -v
A suíte contém 15 testes automatizados para tamanhos, categorias, erros, quantidades e interface de linha de comando. A execução local e no Colab deve ser conferida antes da submissão; resultados prévios não dispensam novos testes.
Estrutura do repositório
GeradorSenhasUFG/
├── gerador_senhas.py
├── GeradorSenhasUFG_Colab.ipynb
├── tests/test_gerador_senhas.py
├── docs/
│   ├── prompts.md
│   ├── roteiro_demo.md
│   ├── entrega_forum.md
│   └── publicar_github.md
├── .github/workflows/testes.yml
├── .gitignore
├── LICENSE
├── README.md
├── pyproject.toml
└── requirements.txt
Como a IA generativa ajudou
A IA auxiliou no planejamento, elaboração de uma primeira implementação, criação de testes e documentação. O processo exemplifica esboçar → testar → avaliar → refinar, documentado em docs/prompts.md. A decisão sobre escopo, revisão final e validação das funcionalidades pertence ao estudante.
Decisões e limitações
- O módulo secrets, em vez de random, fornece a fonte de aleatoriedade usada para senhas.
- O embaralhamento usa uma variante do algoritmo Fisher-Yates com secrets.randbelow().
- As funções de geração são separadas da interface de terminal para facilitar testes.
- As senhas são exibidas na tela e não são gravadas pelo programa; evite compartilhar a saída ou armazená-la em logs.
- O trabalho é um exercício educacional, não uma auditoria de segurança e não substitui um gerenciador de senhas.
- Se restringir o conjunto de caracteres a poucas categorias, a robustez da senha pode cair; prefira senhas longas e diversas.
Publicação no GitHub e entrega
1. Crie um repositório no GitHub e envie os arquivos deste diretório (não envie a pasta __pycache__).
2. Verifique se o README aparece na página do repositório e se o workflow de testes está aprovado em Actions.
3. Atualize o modelo docs/entrega_forum.md com o link público verdadeiro e com os testes efetivamente executados por você.
4. Publique no fórum Mini-projeto com IA Generativa, Unidade 5 do Laboratório Introdutório (C4), e interaja com um(a) colega.
Consulte docs/publicar_github.md e docs/roteiro_demo.md para mais detalhes.
Licença
Distribuído sob a licença MIT. Consulte o arquivo LICENSE.
