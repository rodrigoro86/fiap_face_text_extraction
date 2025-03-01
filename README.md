# Face & Text Extraction
Projeto Avaliativo FIAP - Cognitive Environments - 7DTS

## Participantes

| Nome                                 | RM     |
|--------------------------------------|--------|
| Gabriela Schroder de Barros         | 353512 |
| Rodrigo Broslavschi de Oliveira      | 353534 |
| Yuko Suga                            | 355013 |

---

## Definição

Os projetos devem ser elaborados com base nas especificações fornecidas nos materiais anexados.
A entrega deve ser feita, preferencialmente, por meio de um repositório no GitHub, acompanhado de um arquivo de texto contendo a URL pública do repositório. Caso haja dificuldades em utilizar o GitHub, os notebooks podem ser anexados diretamente.

### Entrega Mínima:
- Notebook(s) Jupyter com o desenvolvimento do projeto.
- Artefatos utilizados, como imagens, datasets, features transformadas, entre outros.

### Entrega Adicional (Opcional):
- Desenvolvimento de um aplicativo utilizando **Streamlit**, publicado no **StreamlitCloud**.
- Envio da URL pública da aplicação Streamlit. A criação e publicação do aplicativo no StreamlitCloud poderão conceder até **1 ponto adicional** na avaliação do projeto.

### Instruções Adicionais:
- Quaisquer modelos utilizados devem obrigatoriamente utilizar **serviços em cloud**, não importa o provedor, recomendando aqueles estudados em aula, como **AWS** e **OpenAI**.
- Não será permitido o uso de modelos criados sem o uso de cloud.
- Os modelos de disciplinas anteriores, como **Computer Vision**, não podem ser reutilizados.
- Os notebooks devem demonstrar claramente **todo o processo de exploração, análise e treinamento do modelo**.
- Caso o grupo opte por desenvolver o aplicativo **Streamlit**, este deve ser **funcional e permitir a interação** com o modelo desenvolvido.
- A entrega dos projetos será avaliada com base na **completude, qualidade da análise e implementação**, além da **clareza e organização** dos notebooks e artefatos entregues.
- O ponto adicional pelo aplicativo Streamlit será concedido considerando a **funcionalidade e usabilidade da aplicação**.

---

## Descrição do Projeto

O setor de fraudes apontou que existem clientes que se queixaram de **não contratar serviços específicos**, como o crédito pessoal. Entretanto, após a análise do **indicador de Detecção de Vivacidade (liveness)**, desenvolvido na disciplina de **Computer Vision**, foi identificado que algumas imagens apresentavam um percentual de vivacidade **menor que 90%**.

Com isso, surgiu a necessidade de uma nova validação do **selfie da pessoa com o documento oficial**, garantindo maior segurança na autenticação.

---

## Implementação do Projeto

### Tecnologias Utilizadas:
- **Python**
- **Jupyter Notebook**
- **AWS Textract** (OCR para extração de informações da CNH e comprovante de endereço)
- **AWS Rekognition** (Comparador de faces para validação biométrica)
- **OpenCV, Pillow e Matplotlib** (Para manipulação de imagens)

### Etapas do Desenvolvimento:

1. **Leitura das imagens:**
   - CNH (imagem oficial do documento do usuário)
   - Foto de comparação (selfie do usuário)
   - Comprovante de endereço

2. **Extração de Informações via OCR:**
   - Uso do **AWS Textract** para extrair nome e CPF da CNH.
   - Extração de endereço do comprovante.

3. **Conversão das imagens para bytes:**
   - As imagens precisam ser convertidas para bytes para envio ao **AWS Rekognition**.

4. **Comparador de Faces:**
   - O **AWS Rekognition** é utilizado para validar a similaridade entre a foto da CNH e a selfie enviada pelo usuário.
   - O sistema destaca a similaridade e sinaliza casos de baixa correspondência.

5. **Exibição das Imagens Processadas:**
   - Uso do **Pillow** e **Matplotlib** para renderizar as imagens processadas e destacadas.

---

## Resultados Esperados
- **Extração automática de informações** (nome, CPF, endereço) sem digitação manual.
- **Comparador de faces confiável**, baseado na tecnologia da AWS.
- **Possibilidade de expansão** para uso comercial e em sistemas de validação.

---

## Como Executar o Projeto

1. **Configurar credenciais da AWS:**
   - Criar um arquivo `.env` com as variáveis de ambiente:
     ```env
     AWS_CHAVE_DE_ACESSO=seu_access_key
     AWS_CHAVE_SECRETA=seu_secret_key
     ```

2. **Instalar dependências:**
   ```bash
   pip install boto3 opencv-python pillow matplotlib python-dotenv
   ```

---

## Considerações Finais
O projeto **Face & Text Extraction** tem como objetivo aumentar a segurança e reduzir fraudes em autenticação de identidade. Ele utiliza serviços **cloud-based** para extração e validação automática de informações, garantindo rapidez e confiabilidade no processo.

