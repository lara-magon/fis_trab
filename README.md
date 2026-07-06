# fis_trab

import tkinter as tk
from tkinter import messagebox
import math

MU0 = 4 * math.pi * 1e-7

def calcular():

    try:
        I = float(entrada_corrente.get())
        a = float(entrada_lado.get()) / 100

        if I <= 0 or a <= 0:
            raise ValueError


        r = a / math.sqrt(2)

        Bfio = MU0 * I / (2 * math.pi * r)

        componente = Bfio / math.sqrt(2)

        Bx = 0

        By = 4 * componente

        B = math.sqrt(Bx**2 + By**2)

        resultado.config(
            text=f"Bx = {Bx:.6e} T\n"
                 f"By = {By:.6e} T\n\n"
                 f"Campo Magnético Resultante\n"
                 f"B = {B:.6e} T"
        )

    except ValueError:
        messagebox.showerror(
            "Erro",
            "Digite apenas números positivos."
        )


def limpar():
    entrada_corrente.delete(0, tk.END)
    entrada_lado.delete(0, tk.END)
    resultado.config(text="")


janela = tk.Tk()
janela.title("Calculadora Campo Magnético")
janela.geometry("420x320")
janela.resizable(False, False)

titulo = tk.Label(
    janela,
    text="CALCULADORA DO CAMPO MAGNÉTICO",
    font=("Arial", 14, "bold")
)
titulo.pack(pady=10)

tk.Label(janela, text="Corrente (A)").pack()

entrada_corrente = tk.Entry(janela, justify="center")
entrada_corrente.insert(0, "20")
entrada_corrente.pack()

tk.Label(janela, text="Lado do quadrado (cm)").pack(pady=5)

entrada_lado = tk.Entry(janela, justify="center")
entrada_lado.insert(0, "20")
entrada_lado.pack()

tk.Button(
    janela,
    text="CALCULAR",
    command=calcular,
    width=20,
    bg="lightgreen"
).pack(pady=10)

tk.Button(
    janela,
    text="LIMPAR",
    command=limpar,
    width=20
).pack()

resultado = tk.Label(
    janela,
    text="",
    font=("Courier New", 11),
    justify="left"
)
resultado.pack(pady=15)

tk.Button(
    janela,
    text="SAIR",
    command=janela.destroy,
    width=20,
    bg="tomato"
).pack()

janela.mainloop()
