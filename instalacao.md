# Relatórios Manutenção e Montagem de computadores
## aula 6 26/10/2023
### **Estudante:** Geise Silva

# instalação de sistema operacinal
a instalação de um sistema operacional é feita atraves de um pen-drive bootavel, primero reiniciamos o sistema e clicamos na tecla f12 assim que o sistema ouver reiniciado em outra tela selecione o pendrive e comece a configuração para instalar o sistema operacional. quando a instalação ouver terminado configure o sistema final.
----------------
## Partições Lógica
Uma partição lógica é um volume criado dentro de uma partição estendida em um disco básico baseado em MBR (registro de inicialização de master).

Partições lógicas são semelhantes a partições primárias. No entanto, embora apenas quatro partições primárias possam existir em um único disco, o número de partições lógicas que podem existir em um disco é ilimitado. Uma partição lógica pode ser formatada e atribuída uma letra de unidade. Uma partição lógica deve ser criada dentro de uma partição estendida. Se uma partição estendida ainda não existir no disco ou o tamanho especificado da unidade lógica exceder a partição estendida, nenhuma partição será criada.
## Partição Prímaria
Você pode dividir um disco rígido em duas partições: Partição primária e partição estendida. Uma unidade de disco pode ter no máximo quatro partições primárias e cada uma pode ter seu sistema operacional. Dito isso, apenas uma partição primária pode estar ativa e as outras ficarão ocultas. Uma partição primária possui um tipo de código que indica o sistema de arquivos que contém ou se possui ou não um uso específico.

Vejamos algo que facilita a memorização de uma partição primária: Se você precisa da unidade para ser inicializável, ela deve ter uma partição primária. Além disso, um disco rígido requer pelo menos uma partição primária. Você pode, também criar uma partição primária usando o DiskPart.
## Partição estendida
Uma partição estendida só pode ser criada em discos baseados em registro de inicialização master (MBR).

Somente uma partição estendida pode existir em um único disco. Se uma partição estendida já existir no disco, uma segunda partição estendida não será criada. Se o valor da configuração WillShowUI estiver definido como Nunca, um erro será registrado e a instalação será encerrada.

Partições estendidas serão úteis se você pretende criar mais de quatro volumes em um disco MBR básico. Ao contrário das partições primárias, você não formata uma partição estendida com um sistema de arquivos. Em vez disso, você cria uma ou mais unidades lógicas dentro da partição estendida.
## Partição Swap
Este tipo de partição é usado para oferecer o suporte a memória virtual ao GNU/Linux em adição a memória RAM instalada no sistema. Este tipo de partição é identificado pelo tipo 82 nos programas de particionamento de disco para Linux. Para detalhes de como criar uma partição Linux Swap veja “Criando sistema de arquivos Swap em uma partição”.

Somente os dados na memória RAM são processados pelo processador, por ser mais rápida. Desta forma quando você está executando um programa e a memória RAM começa a encher, o GNU/Linux move automaticamente os dados que não estão sendo usados para a partição Swap e libera a memória RAM para a continuar carregando os dados necessários pelo. Quando os dados movidos para a partição Swap são solicitados, o GNU/Linux move os dados da partição Swap para a Memória. Por este motivo a partição Swap também é chamada de Troca ou memória virtual.

A partição swap é otimizada para permitir alta velocidade para mover dados da memória RAM para ela e vice versa. Note também que é possível criar o sistema de arquivos Swap em um arquivo ao invés de uma partição
----------------
# Freeze S.O
Para quem não conhece, Deep Freeze é uma ferramenta que permite “congelar” o sistema operacional e fazer com que alterações feitas na interface e nos arquivos sejam nulas e voltem ao padrão estabelecido após uma reinicialização. Este é o mesmo conceito do Deep Lock, uma ferramenta brasileira ideal para ser utilizada em escolas, centros educacionais e LanHouses.

O Deep Lock é uma ferramenta nacional oriunda do projeto DuZeru GNU/Linux e feita pensada na versão educacional do sistema, o EduZeru, utilizada atualmente em algumas escolas e universidades do país. Seu funcionamento é muito semelhante ao Deep Freeze para Windows, ele é uma combinação de várias ferramentas diferentes em prol de um resultado, manter o seu sistema íntegro pelo tempo que for necessário, ideal para ser utilizado em laboratórios de informática ou computadores que são acessados pelo público em geral.
## MBR

MBR é uma sigla para"Master Boot Record". é o primeiro setor de disco rígido que contém nformações especificas relacionadas ao sistema operacional usado para inicializar a máquina. Outras denominações para o registro mestre de inicialização são "setor zero", "bloco de inicialização mestre" ou "setor de inicialização de participação mestre". MBR era um formato de tabela de partição padrão quando  o tamanho dos discos rígidos era inferior a 2 TB porque esse é o tamanho máximo do disco rígido compatível com MBR. Na verdade, com discos rígidos maiores, se você usar MBR, apenas 2 TB de seu enorme disco rígifo estarão acessíveis; foi quando o **formato GPT** surgiu.

##  GPT

Assim como o MBR, o GPT também armazena dados essenciais do disco, incluindo partições partições  e tamanhos, em um setor com um endereço de bloco lógico (LBA) de 1. A diferente é que, mesmo ao usar a partição GPT, o disco precisa manter um setor para compatibilidade com MBR e BIOS , portanto, tecnicamente, o primeiro setor do disco ainda é dedicado ao MBR e não pode ser usado como detentor de chave do GPT. Isso não significa que o primeiro setor precisa ser chamado de LBA 1! portanto, no GPA, o LBA 0 é atribuido ao primeiro setor (ou seja, o setor MBR), de modo que o GPT pode ter o proximo setor como LBA 1.  

-----------------------
## REFERÊNCIA 
Bibliografia
Partição Linux Swap (Memória Virtual). ([s.d.]). Guiafoca.org. Recuperado 23 de novembro de 2023, de https://www.guiafoca.org/guiaonline/intermediario/ch05s07.html

Santos, L. ([s.d.]). Partição primária vs partição lógica: Qual a diferença? Com.br. Recuperado 23 de novembro de 2023, de https://recoverit.wondershare.com.br/partition-tips/primary-partition.html

windows-driver-content. ([s.d.]). Tipo. Microsoft.com. Recuperado 23 de novembro de 2023, de https://learn.microsoft.com/pt-br/windows-hardware/customize/desktop/unattend/microsoft-windows-setup-diskconfiguration-disk-createpartitions-createpartition-type

([S.d.]). Recuperado 23 de novembro de 2023, de http://ttps://diolinux.com.br/sistemas-operacionais/deep-lock-um-alternativa-ao-deepfreeze-linux.html#:~:text=Para%20quem%20não%20conhece%2C%20Deep,padrão%20estabelecido%20após%20uma%20reinicialização.