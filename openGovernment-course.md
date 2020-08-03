# Open Government - Delft University MOOC course

## Módulo 1

#### Introdução ao Governo Aberto.

* Abertura > Transparência > Accountability > Participação cívica > Confiança

#### Desenvolvimentos das TICs influenciando o Governo Aberto.

* Desafio, problema ou necessidade do usuário em vez de conteúdo ou informação dada pelo governo

* Search engines, data API, mash-ups, semantic data, linked data, data analytics

* Escolher texto correto para indexação do portal na web exige um conhecimento de como os usuários buscam pelos dados constantes no portal

* Keywords ou linguagem natural; metadados e tags humanas ou automáticas;

* API: interface para acessar dado atualizado automaticamente e em tempo real

* Mash-up: única interface visual de múltiplos recursos de dados

* Semantic data: descrição do significado do dado de uma maneira estruturada (RDF, OWL, protocolos...)

* Linked data: relacionamento de dados (RDF, p. ex), aplicações podem usar links para inferir sem intervenção humana - teia semântica

#### Evolução do Governo Digital.

* + eficiência e qualidade; melhores serviços públicos em canais eletrônicos; facilitar reforma administrativa e institucional no governo; engajar cidadãos no processo decisório; apoiar políticas e objetivos em setores específicos e localidades

* estágio 1 = digitalização (tecnologia no governo): portais;
 estágio 2 = transformação (governo eletrônico): permitir colaborãção entre agências governamentais;
 estágio 3 = engajamento (governança eletrônica);
 estágio 4 (especialização): e-saúde, e-educação, comunidades locais nas decisões

 * consultas e ideação por cidadãos + orçamento participativo + crowdsourcing são inovações permitem liberdade de informação, governo aberto e citizens sourcing

#### Partes interessadas em Governo Aberto.

* Ator (usuário, político, desenvolvedor) X stakeholder (interesses em jogo - pode ser indivíduo ou grupo, primário/direto ou secundário/indireto);

* Atributos stakeholders = poder, legitimidade, urgência

* tensões entre governo e sociedade civil sobre oferta e demanda de dados abertos: granularidade do dado, custo da abertura, facilidade de uso (maioria dos esforços estão na oferta);

* risco para o público = capacitação dos stakeholders já opderosos; construir capacidades e conhecer o público

* provedores de infraestrutura: custo e esforços elevados; papel central (ONG não lucrativa na Holanda)

* infomediares: agregam e analisam informação; confiança; compreensão de usuários e postulação de padrões ideais de governo aberto;

* estratégias: compreender usuários; obter compromisso de políticos e organizações; criar senso de urgência associando dados a problemas da sociedade; valorizar input do usuário; organizar eventos e treinar usuários 

#### Ciclo de Elaboração de Políticas.

* processo complexo interativo, de consenso difícil, no qual até mesmo a definição dos problemas não são triviais; 

* racionalidade limitada: informação incompleta, múltiplas opções, incerteza de critérios de avaliação, trade-offs, resultados imprevisíveis, 

* influência do governo aberto: exploração da opinião e análise dos sentimentos; simulações; IoT; open dashboards; crowdsourcing - cidadãos como inovadores (hackatons, p. ex.)

## Módulo 2 - abrindo e reutilizando dados do governo

#### O que são Dados Abertos do Governo?

* abertura, governo, dado e usabilidade

* dados devem ser estruturados, legíveis por máquina, publicamente reutilizáveis, acessados gratuitamente e sem restrições (licenças ou infraestruturas não amigáveis), na internet

* modelo de 5 estrelas de Berners-Lee (pdf > xls > csv > rdf dados linkados) Dados Abertos vinculados no formato RDF (Resource Description Framework) recebem cinco de cinco estrelas na escala de implantação de cinco estrelas de Berners-Lee e estão a nível ideal, o que é visto como o melhor nível possível de ser alcançado. Nesse nível ideal, os Dados Abertos estão vinculados a outros dados para fornecer contexto, através, por exemplo, do Resource Description Framework, ou RDF.

* eurostats, publicspending.net; 

#### Processos de Dados de Governo Aberto: da coleta de dados ao uso de dados.

* coleta e publicação (governo), busca e uso (usuário)

* cleansing, analyzing, visualizing, enriching, linking and combining

* categorias de usuários: empresários, desenvonvedores, cidadãos, pesquisadores, jornalistas, arquivistas, bibliotecários, funcionários públicos

#### Considerações ao abrir dados do governo

* aspectos para abertura de cada dataset: responsabilidade pela publicação (várias organizações concorrem para o mesmo dataset), períodos de embargo, níveis de abertura (proteção, custo), sensibilidade e privacidade, qualidade e integridade (usuários podem ajudar o editor ou simplesmente não perceber erros), documentação (significado e semântica claros), trade-off entre benefícios e prejuízos/riscos (decisões revisadas de tempos em tempos)

Quando um organismo público coleta dados para um determinado fim, estes dados podem ser utilizados para outros fins, quando se tornarem disponíveis ao público. O provedor de dados não pode determinar, antecipadamente, em que medida os dados são importantes, uma vez que isso depende da finalidade de seu uso. Muitas vezes, os órgãos públicos, primeiro, publicam dados que eles acham que são mais importantes para os usuários de dados em potencial, porém, isso é uma estimativa, e a importância dos dados não pode ser medida objetivamente antes que os dados sejam publicados e utilizados.

Alternativa a: Uma consideração importante ao abrir os dados do governo refere-se à qualidade e à integralidade dos dados. Funcionários públicos podem decidir divulgar dados sem terem noção de sua qualidade. Como consequência, eles podem publicar dados que estão incompletos, imprecisos, inválidos ou que não são confiáveis. Os usuários podem comentar os dados, tentar aumentar sua qualidade e isso pode criar um incentivo para o editor de dados melhorar os dados. Em contraste, usuários podem não notar que os dados são de má qualidade. Dados de baixa qualidade podem ser reutilizados e decisões e conclusões podem ser baseadas nesses dados. Um conjunto de dados com muitos valores ausentes ou variáveis pode ser mal interpretado ou pode não ser útil a todos. Conjuntos de dados, portanto, antes que possam ser publicados, precisam ter um certo nível de qualidade e integralidade.

Alternativa ‘b’: Sensibilidade de dados e aspectos legais são importantes quando os organismos públicos consideram a abertura de seus dados. Pode ser muito difícil determinar o limite entre dados sensíveis e não sensíveis, especialmente porque isso precisa ser feito individualmente para cada conjunto de dados. A decisão sobre a sensibilidade dos dados exige interpretação e erros podem ser cometidos. Potenciais efeitos negativos de não revelar certos dados são que apenas os dados disponibilizados favorecem determinados argumentos ou decisões dos políticos. Então, os Dados Abertos denotam algum tipo de viés e uma perspectiva realista pode ser criada a partir dos conjuntos de dados divulgados.

Alternativa ‘c’: Uma consideração importante diz respeito à documentação de dados. Para serem capazes de usar os Dados Governamentais Abertos, os usuários precisam ter algumas informações sobre o significado dos dados e a semântica precisa ser clara. Eles precisam de documentação para entender como os dados podem ser utilizados. Por exemplo, para ser capaz de encontrar um livro na biblioteca, uma pessoa precisa saber para que categoria se deve olhar. No entanto, acrescentar uma considerável documentação aos conjuntos de dados governamentais exige esforço e investimento de tempo pelo provedor de dados, pois muitas vezes essa informação não pode ser obtida automaticamente a partir dos dados dos sistemas do provedor.

#### Portais de Dados Abertos.

* definição: panorama dos dados disponíveis, link entre o usuário e o provedor (geralmente, o dado não está no portal, para evitar publicação de versões múltiplas, capacidade adicional de hospedagem e atualizações)

* elementos: tornar dados pesquisáveis e possíveis de serem encontrados (pela qualidade e quantidade de metadados, APIs e dados linkados)

## Módulo 3 - Aspectos Técnicos e Legais

#### Análise Aberta de Dados de Pesquisa

* coleta: observação, survey, experimento, simulação; licenças convergem para CC-BY;

* variedade, volume, velocidade, validade e valor

* etapas para análise: descoberta, contextualização (tempo, espaço, precisão), conexão (API) e análise (software para correlação, p. ex) 

* virtual research environment (European Plate Observing System/EPOS, ENVRIPlus, PaaSage)

#### Metadados para Dados de Governo Aberto

* classificação por uso (descoberta, contexto e detalhe);

* padrões: DC - Dubline Core (descreve páginas da web), CKAN (para governos), eGMS, CERIF (informações sobre pesquisas), DCAT (datasets da web também baseado no DC), INSPIRE (geospaciais)

#### Aspectos Legais dos Dados de Governo Aberto

* dado conhecido (publicado na web), disponível (software para uso) e utilizável (claro, manejável e confiável - metadados)

* desafios: muitos datasets que juntos podem ser considerados pessoais; qual das várias licenças existentes deve ser utilizada; como gerar interoperabilidade no nível regional ou nacional; questões de confiança como erros, dados de terceiros

#### Tecnologias para Dados Abertos Vinculados

* dados abertos vinculados (linked open data) = devem ter semântica legível por máquinas; estrutura comun que permitem seu reuso em outros domínios; RDF, vocabulários (OWL), 

* princípios: uso de URI (identificadores únicos de recursos), uso de HTTP para identificar objetos, uso de um único modelo de dados para publicação (RDF), uso de hiperlinks

* tecnologias: RDF permite mix de vocabulários distintos para representar dados, num tripé 'sujeito-predicato-objeto' (mas não fornece significado legível por gente ou máquina)

* ontologia: descrição exata das coisas (significado = semântica) e seus relacionamentos; OWL - padrão internacional

* lod-cloud.net = linked datasets

## Módulo 4 - Governo Aberto e valores públicos

#### Governo Aberto e transparência

* redução da lacuna de assimetria de informação entre governo e seus constituintes;

* dados são necessários, mas não suficientes - interações requeridas para insights do público e informações contextuais são requeridas para que dados se transformem em informações

* fatores do nível de transparência: nível de interação, coleta de informação adicional, disponibilidade de dados sobre contexto, clareza da informação e tipo da tecnologia

* transparência é condição necessária, mas não suficiente, para accountability

#### Participação no Governo Aberto



#### Estratégias de preservação de privacidade no Governo Aberto

* revogação de identidade face à data linkage (recuperação de perfis);

* estratégias de preservação da privacidade: anonimização, troca de quasi-identifiers (gÊnero e residência), remoção de dados sensíveis, publicação de dados que sejam não-pessoais 