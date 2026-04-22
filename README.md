# RC Low-Pass Filter — Transfer function derivation

## 1. Circuit Description
- Resistor R in series with input  
- Capacitor C connected to ground  
- Output taken across the capacitor  


## 2. Transfer Function Definition
H(s) = V_out(s) / V_in(s)


## 3. Impedance Representation (Laplace Domain)
Z_R = R  
Z_C = 1 / (sC)


## 4. Apply Voltage Divider Rule
V_out = V_in × (Z_C / (Z_R + Z_C))

Substitute:
V_out = V_in × [ (1 / sC) / (R + 1 / sC) ]


## 5. Simplification
Multiply numerator and denominator by sC:

V_out = V_in × [ 1 / (sRC + 1) ]



## 6. Final Transfer Function
H(s) = 1 / (1 + sRC)

--

# RC Band-Pass Filter — Transfer function derivation

## 1. Circuit Description
- High-pass stage: capacitor C₁ in series, resistor R₁ to ground  
- Low-pass stage: resistor R₂ in series, capacitor C₂ to ground  
- Output taken after the low-pass stage  
- Circuit: Input → HPF → LPF → Output  



## 2. Transfer Function Definition
H(s) = V_out(s) / V_in(s)



## 3. High-Pass Stage Derivation

Impedances:
Z_C₁ = 1 / (sC₁)  
Z_R₁ = R₁  

Voltage divider:
V₁ = V_in × (R₁ / (R₁ + 1/(sC₁)))

Simplify:
H_HP(s) = V₁ / V_in = sR₁C₁ / (1 + sR₁C₁)



## 4. Low-Pass Stage Derivation

Impedances:
Z_R₂ = R₂  
Z_C₂ = 1 / (sC₂)

Voltage divider:
V_out = V₁ × (Z_C₂ / (R₂ + Z_C₂))

Simplify:
H_LP(s) = V_out / V₁ = 1 / (1 + sR₂C₂)



## 5. Overall Transfer Function

Since stages are cascaded:

H(s) = H_HP(s) × H_LP(s)

H(s) = [sR₁C₁] / [(1 + sR₁C₁)(1 + sR₂C₂)]

---

# RLC Band-Pass Filter - Transfer function derivation

## 1. Circuit Assumption
We consider a **series RLC circuit** where:
- Input voltage: Vin is applied across the entire circuit  
- Output voltage: Vout is taken across the resistor R  



## 2. Impedances in Laplace Domain

ZR = R  
ZL = sL  
ZC = 1 / (sC)

Total impedance:

Ztotal = R + sL + 1/(sC)



## 3. Voltage Divider Rule

Vout = Vin × (ZR / Ztotal)

So,

Vout / Vin = R / (R + sL + 1/(sC))



## 4. Raw Transfer Function

H(s) = Vout / Vin = R / (R + sL + 1/(sC))



## 5. Convert to Polynomial Form

Multiply numerator and denominator by sC:

Numerator:
R × sC

Denominator:
(R + sL + 1/(sC)) × sC  
= RsC + s²LC + 1

So,

H(s) = (RsC) / (s²LC + RsC + 1)



## 6. Normalize the Expression

Divide numerator and denominator by LC:

Numerator:
(R/L) × s

Denominator:
s² + (R/L)s + 1/(LC)



## 7. Final Transfer Function

H(s) = [(R/L)s] / [s² + (R/L)s + 1/(LC)]



## 8. Key Parameters

Resonant frequency:
ω₀ = 1 / √(LC)

Bandwidth:
BW = R / L

Quality factor:
Q = (ω₀L) / R



## 9. Interpretation

- LC determines the resonant frequency  
- R controls the bandwidth  
- The numerator term (s) removes low frequencies  
- The circuit passes signals mainly around the resonant frequency
