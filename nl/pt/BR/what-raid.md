---
copyright:
  years: 2017, 2018
lastupdated: "2018-04-02"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Sobre RAID

O RAID (Redundant Array of Independent Disks) cria um único disco de dados utilizáveis, em que vários discos físicos são combinados em uma matriz para melhor velocidade e tolerância a falhas. 
A seguir estão os três conceitos principais em RAID:
* Espelhamento: copiando os dados para mais de um disco
* Striping: dividindo os dados em mais de um disco
* Correção de erro (tolerância a falhas): os dados redundantes são armazenados para permitir que os problemas sejam detectados e
possivelmente corrigidos.

Embora existam vários níveis diferentes de RAID, a IBM opta por suportar os tipos de RAID mais comuns: 0, 1, 5 e 10. Os diferentes níveis do RAID usam uma ou mais das técnicas a seguir, dependendo dos requisitos do sistema. O principal propósito é usar RAID para melhorar a confiabilidade usando 3Ware 9550SX RAID SATA ou um controlador Adaptec SA-SCSI RAID para todas as soluções RAID implementadas.

O RAID não é uma Solução de backup.  O RAID cria um disco de dados utilizáveis único, no qual vários discos físicos são combinados em uma matriz para melhor velocidade e/ou tolerância a falhas.


**RAID 0** (Conjunto dividido sem paridade/matriz não redundante) Implementa a separação de dados em faixas em que os blocos de arquivo são gravados em múltiplas unidades em fragmentos e requer um mínimo de dois discos. A vantagem de um RAID 0 é que a velocidade de leitura/gravação é significativamente aumentada. Quanto mais discos existem na matriz, maior a largura da banda. 
A desvantagem de um RAID0 é não ter tolerância a falhas. Então, se uma única unidade falha, ela destrói a matriz. Além disso, um RAID 0 não implementa a verificação de erro. Então qualquer erro também é irrecuperável. 
Uma solução comum para a tolerância a falhas é ter uma unidade fora da matriz usada como armazenamento de backup em uma falha
de hardware.

**RAID 1** (Conjunto espelhado sem paridade) Implementa o espelhamento de dados. Os dados são duplicados em 2 ou 4 unidades por meio de um controlador RAID de hardware e fornecem alguma tolerância a falhas. A matriz será recuperável se pelo menos uma unidade não falhar. 
Ela fornecerá um desempenho de leitura mais rápido do que uma unidade única e redundância de unidade se uma falha ocorrer. 
A velocidade de gravação também será ligeiramente reduzida.

**RAID 5** (Conjunto dividido com paridade distribuída dual) Implementa a separação de dados em faixas em um nível de bloco e distribui a paridade entre as unidades. As informações de paridade permitem a recuperação da falha de qualquer unidade única porque quaisquer leituras seguintes podem ser calculadas da paridade distribuída. O RAID 5 também permite o aumento de velocidades de leitura/gravação e permite o uso mais eficiente de espaço em disco. O RAID 5 requer um mínimo de três discos.

**RAID 10** (RAID 1 + 0) Cria múltiplos espelhos, em que os dados são organizados como faixas em múltiplos discos e, então, os conjuntos de discos divididos são espelhados. O RAID 10 oferece a mesma tolerância a falhas que o RAID 1 com o aumento de velocidades de leitura/gravação de mais de um volume RAID 1 único ou unidade única. O nível do RAID 10 requer quatro unidades para implementar.
