
# DTMF Decoder Using Integer-Based DSP

## Overview

This project implements a **Dual-Tone Multi-Frequency (DTMF) Decoder** using integer-based digital signal processing (DSP) techniques. DTMF is the standard used in telecommunication systems to encode keypresses as pairs of audio frequencies. The decoder processes input audio signals to determine the corresponding keypad symbols while adhering to the DTMF standard.

The project was designed as part of a coursework assignment to explore digital filter design, integer arithmetic in DSP, and minimizing **Inter-Symbol Interference (ISI)** for improved communication rates.

## Features

- Decodes DTMF signals into corresponding keypad symbols.
- Implements **integer-based filters** for computational efficiency.
- Supports **narrow bandpass filters** for high selectivity.
- Adheres to the DTMF standard frequencies:
  - Low frequencies: 697 Hz, 770 Hz, 852 Hz, 941 Hz
  - High frequencies: 1209 Hz, 1336 Hz, 1477 Hz, 1633 Hz
- Measures and minimizes ISI to improve detection accuracy during symbol transitions.

## System Design

### High-Level Block Diagram

The system includes the following components:
1. **Signal Detection**: Detects the presence of specific DTMF tones using bandpass filters.
2. **Rectification and Low-Pass Filtering**: Processes the filtered signal to compute the DC value.
3. **Threshold Comparison**: Determines if the tone is present by comparing the filtered signal against a predefined threshold.
4. **Symbol Decoding**: Combines detected frequencies to identify the corresponding keypad symbol.

*See the project documentation for detailed block diagrams.*

### Key Performance Metrics

- Achieved ISI: ~18% for fast signals, ~7.8% for slow signals.
- Integer-based filter coefficients for optimized computation:
  - Example: `b0 = 128`, `a1 = -108`, `a2 = 108` (scaled by `C = 128`).

## Technical Details

- **Programming Language**: Python
- **Digital Filters**: Implemented using integer coefficients to enhance efficiency on DSP systems.
- **Development Tools**:
  - MATLAB for filter design and analysis.
  - Python for simulation and implementation.
- **Sampling Rate**: 4000 Hz
- **Filter Design**:
  - Bandpass filters are designed using pole-zero placement.
  - Integer coefficients are computed by scaling and rounding fractional values.

## Results

- Successfully decoded DTMF signals while maintaining low ISI.
- Optimized filter designs for integer-based computation with reduced round-off errors.
- Demonstrated efficient detection of symbols even under faster communication rates.

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/dtmf-decoder.git
   cd dtmf-decoder
   ```

2. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the decoder:
   ```bash
   python cpe367_dtmf.py
   ```

4. View results:
   - The output includes detected symbols and performance metrics such as ISI.

## Improvements

Future enhancements could include:
- **Dynamic ISI Reduction**: Implement adaptive thresholds for symbol transitions.
- **Higher-Order Filters**: Improve frequency selectivity and reduce ISI.
- **Support for Real-Time Decoding**: Extend the system to process live audio signals.

## Acknowledgments

This project was developed as part of the *CPE 367 - Digital Signal Processing* course under the guidance of Dr. F. DePiero. The project incorporates concepts such as integer-based filter design, DTMF decoding, and ISI optimization.
