<img width="533" height="384" alt="image" src="https://github.com/user-attachments/assets/1c438aab-a68e-46d1-9957-ac830713b32d" />


# **Detecção de Máscara Facial em Tempo Real**
**1. Introdução**
   
Este projeto implementa um sistema de detecção de máscara facial utilizando OpenCV e um modelo de deep learning treinado em Keras/TensorFlow. A aplicação funciona em tempo real, acessando a webcam do usuário para identificar se a pessoa está usando máscara ou sem máscara.

**2. Funcionamento do Projeto**

- O programa abre a webcam e captura os frames em tempo real.

- Utiliza o classificador Haar Cascade para detectar rostos em cada frame.

- Cada rosto detectado passa por um pré-processamento:
  
   a) recorte da região do rosto,

   b) redimensionamento para 224 × 224 pixels,

   c) normalização dos valores de pixel (0–1).

- O modelo treinado (mask_detector.h5) faz a predição, classificando o rosto como:

    a) Mask (com máscara)

    b) No Mask (sem máscara)

- O resultado é exibido em tempo real com um retângulo em volta do rosto:

    a) Verde para “Mask”

    b) Vermelho para “No Mask”

    c) Probabilidade (%) da predição.

- O sistema é encerrado quando o usuário pressiona a tecla ESC.

**3. Estrutura do Código** 

- Carregamento do modelo: mask_detector.h5 (rede neural treinada).

- Labels e cores: 0 = Mask (verde), 1 = No Mask (vermelho).

- Captura de vídeo: cv2.VideoCapture(0) para abrir a webcam.

- Detecção de rostos: haarcascade_frontalface_default.xml.

- Predição: o modelo avalia cada rosto recortado e retorna o resultado.

- Exibição: uso do OpenCV para mostrar os frames processados em uma janela.

**4. Tecnologias Utilizadas**

- Python 

- OpenCV (cv2) – para captura de vídeo e processamento de imagens.

- NumPy – para manipulação numérica e arrays.  

- TensorFlow/Keras – para carregamento do modelo pré-treinado (.h5).

**5. Resultados Obtidos**

O sistema foi capaz de identificar em tempo real se a pessoa estava utilizando máscara ou não. O feedback visual, por meio de cores e probabilidades, tornou a aplicação intuitiva e de fácil compreensão. Trata-se de uma solução prática, adequada para cenários como o monitoramento em ambientes públicos ou para uso em testes educacionais voltados à visão computacional.

**6. Próximos Passos**

- Melhorar a acurácia treinando o modelo com mais imagens.

- Adicionar suporte a múltiplos rostos simultâneos.

- Criar interface gráfica com Streamlit ou Tkinter.

- Implementar alertas sonoros quando alguém estiver sem máscara.


