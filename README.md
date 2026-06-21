# Instruções de Execução do Notebook - Gnina (Molecular Docking)

Este notebook realiza o docking molecular utilizando a ferramenta `gnina`, faz a visualização 3D das moléculas com `py3Dmol` e calcula o RMSD com `openbabel`.

## Pré-requisitos
1. Certifique-se de que o Colab está configurado para usar uma GPU.
   - Vá no menu superior: `Ambiente de execução` -> `Alterar o tipo de ambiente de execução`.
   - Em `Acelerador de hardware`, selecione `GPU` (ex: T4 GPU) e salve.

## Passos executados no notebook:
1. **Verificação da GPU**: O comando `!nvidia-smi` verifica se a GPU está ativa.
2. **Instalação do Gnina**: Baixa o binário do `gnina` (versão 1.3.2) do GitHub, renomeia e dá permissão de execução.
3. **Preparação dos Arquivos**:
   - Baixa a estrutura 3ERK (formato PDB) do banco de dados RCSB PDB.
   - Extrai as coordenadas do receptor (`rec.pdb`) e do ligante (`lig.pdb`) usando comandos `grep`.
4. **Docking Molecular**: Executa o `gnina` para fazer o redocking do ligante no receptor, gerando o arquivo de saída de poses `docked.sdf`.
5. **Visualização 3D**: Instala e utiliza a biblioteca `py3Dmol` para visualizar o receptor, o ligante cristalizado e a animação das poses geradas pelo docking.
6. **Cálculo de RMSD**: Instala o `openbabel` e utiliza a ferramenta `obrms` para calcular as diferenças estruturais (RMSD) entre as poses geradas (`docked.sdf`) e a estrutura do ligante original (`lig.pdb`).

## Como Executar
Após garantir que a GPU está ativada no ambiente, você pode executar o notebook passo a passo clicando no botão 'Play' ao lado de cada célula, ou simplesmente ir no menu superior e clicar em `Ambiente de execução` -> `Executar tudo` (atalho Ctrl+F9).

