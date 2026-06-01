# Audio Amplifier Project

A multi-stage analog audio amplifier design featuring a pre-amplifier, voltage gain stage, active filter, and complementary push-pull power amplifier output stage. This project implements a complete audio signal conditioning and amplification system suitable for low-power audio applications.

## Project Overview

This audio amplifier is designed to take weak audio signals (from microphones, line-level sources) and amplify them to drive speakers or external audio loads. The design uses a cascaded amplification approach with distinct functional stages, each optimized for its role in the signal chain.

### Key Features

- **Multi-stage Amplification**: Modular design with separate pre-amplifier, gain, filter, and power amplifier stages
- **Low-Noise Pre-amplifier**: Discrete transistor-based front-end using BC547B transistors
- **Op-Amp Voltage Gain Stage**: Precision gain control using UA741 operational amplifier
- **Active Filter Stage**: Frequency response shaping for audio band optimization
- **Complementary Push-Pull Power Amplifier**: High-current output stage using TIP31A/TIP32A transistor pair
- **Wide Frequency Response**: Designed for standard audio band (20Hz - 20kHz)

## Architecture

The amplifier consists of four main stages:

### 1. **Pre-Amplifier Stage** (`pre_amp_stage.asc`)
- Input signal conditioning using BC547B transistors
- Low-noise design for weak signal sources
- Impedance matching and initial signal amplification
- Sets the noise floor for the entire system

### 2. **Voltage Gain Stage** (`gain_stage.asc`)
- Based on the UA741 operational amplifier
- Configurable gain through feedback resistor networks
- Provides stable, predictable voltage amplification
- Signal buffering and impedance transformation

### 3. **Filter Stage** (`filter_stage.asc`)
- Active filter implementation for frequency response control
- Suppresses out-of-band noise and interference
- Optimizes signal quality for audio applications
- Protects output stage from high-frequency transients

### 4. **Power Amplifier Stage** (`power_amplifier.asc`)
- Complementary push-pull configuration with TIP31A (NPN) and TIP32A (PNP)
- High-current output capability for speaker driving
- Quiescent bias circuit for reduced crossover distortion
- Protection diodes (1N4148) for transient protection

## Circuit Files

- **`final_circuit.asc`** - Complete integrated design combining all stages
- **`pre_amp_stage.asc`** - Standalone pre-amplifier circuit
- **`gain_stage.asc`** - Op-amp voltage gain stage
- **`filter_stage.asc`** - Active filtering network
- **`power_amplifier.asc`** - Output power amplifier stage

All files are in LTSpice schematic format (`.asc`)

## Specifications (Typical)

| Parameter | Value |
|-----------|-------|
| Input Signal Level | 10mV - 20mV |
| Output Power | ~1W (depends on load impedance) |
| Frequency Response | 20Hz - 20kHz |
| Total Harmonic Distortion | < 5% (at nominal power) |
| Noise Figure | Low (discrete pre-amp design) |
| Supply Voltage | Dual ±12V |

## Design Considerations

1. **Thermal Management**: Power transistors (TIP31A/TIP32A) require heat sinks for sustained operation
2. **Power Supply**: Low-noise dual power supply recommended for audio quality
3. **Component Matching**: Match transistor pairs in gain stage for best performance
4. **Biasing**: Proper quiescent current setting in power stage is critical for low distortion

## Getting Started

1. **Review the Schematics**: Open circuit files in LTSpice (freeware available)
2. **Simulate**: Use `final_circuit.asc` for transient analysis
3. **Verify BOM**: Check component availability and specifications
4. **Construction**: Build and test each stage separately before final assembly

## Tools Required

- **LTSpice** (free) - For circuit simulation and visualization
- **Prototyping Equipment**: Breadboard, multimeter, oscilloscope (for testing)

## References

- UA741 Op-Amp Datasheet
- TIP31A/TIP32A Power Transistor Specs
- Audio Amplifier Design Principles
- LTSpice Documentation

## Project Files Organization

```
Audio-Amplifier/
├── README.md                 # This file
├── Report.pdf               # Detailed project report
├── bill_of_materials.txt    # Component list and specifications
├── final_circuit.asc        # Complete amplifier schematic
├── pre_amp_stage.asc        # Pre-amplifier stage
├── gain_stage.asc           # Voltage gain stage
├── filter_stage.asc         # Filter network
├── power_amplifier.asc      # Power output stage
├── UA741.asy                # UA741 op-amp symbol
├── tip31a.lib               # TIP31A transistor model
└── tip32a.lib               # TIP32A transistor model
```

## Notes

- This is a discrete analog design suitable for educational purposes
- For professional audio applications, consider integrated audio amplifier ICs
- Proper grounding and shielding are essential for minimizing noise and interference
- Always verify component specifications and ratings before construction

---
