from abc import ABC, abstractmethod
import math

class Figura(ABC):
    @abstractmethod
    def calcular_perimetro(self) -> float:
        pass

    @abstractmethod
    def calcular_area(self) -> float:
        pass

    @abstractmethod
    def obtener_nombre(self) -> str:
        pass

class OctagonoRegular(Figura):
    def __init__(self, lado: float):
        self.lado = lado

    def calcular_perimetro(self) -> float:
        return 8 * self.lado

    def calcular_area(self) -> float:
        return 2 * (1 + math.sqrt(2)) * (self.lado ** 2)

    def obtener_nombre(self) -> str:
        return "Octagono"

if __name__ == "__main__":
    o = OctagonoRegular(3)
    print(o.obtener_nombre())
    print(f"Perímetro: {o.calcular_perimetro():.2f}")
    print(f"Área: {o.calcular_area():.2f}")
