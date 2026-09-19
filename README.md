# Rastreador de objeto em vídeo

Rastreia um objeto ao longo de um vídeo e mede a distância dele até um ponto fixo da
tela. O exemplo usa um vídeo de futevôlei: você seleciona a bola com o mouse e o
programa segue a bola quadro a quadro, desenhando o caminho percorrido.

## Como funciona

1. O OpenCV abre o vídeo e mostra o primeiro quadro
2. Você marca o objeto arrastando o mouse (`selectROI`)
3. O rastreador CSRT do OpenCV segue esse objeto nos quadros seguintes
4. A cada quadro o programa:
   - desenha um retângulo em volta do objeto, com a palavra "Rastreando"
   - calcula a distância entre o centro do objeto e um ponto fixo definido no código
   - escreve "Ponto" na tela quando essa distância fica menor que 20 pixels
   - marca o centro do objeto, formando o rastro do trajeto
5. Se o rastreador perder o objeto, aparece "lost" na tela

A tecla `q` encerra o programa.

## Tecnologias

- Python
- OpenCV (rastreador CSRT)

## Como executar

```bash
pip install opencv-contrib-python
cd PRO-C119
python obj_trk_final.py
```

O vídeo de exemplo `footvolleyball.mp4` já está na pasta.
