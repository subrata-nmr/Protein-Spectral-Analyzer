import argparse
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np

def parse_args():
    parser = argparse.ArgumentParser(description="UV-VIS Spectroscopy CLI")
    parser.add_argument("input_file", help="Input CSV file containing wavelength and intensity columns")
    return parser.parse_args()

def main():
    args = parse_args()

    try:
        data = pd.read_csv(args.input_file)
    except FileNotFoundError:
        print("Error: Input file not found.")
        return None

    plt.figure(figsize=(10, 6))
    plt.plot(data['wavelength'], data['intensity'])
    plt.xlabel('Wavelength')
    plt.ylabel('Intensity')
    plt.title('UV-VIS Spectroscopy Data')
    plt.grid()

    max_wavelength = data['wavelength'].max()
    mean_intensity = data['intensity'].mean()
    std_intensity = data['intensity'].std()

    print(f"Maximum Wavelength: {max_wavelength:.2f}")
    print(f"Mean Intensity: {mean_intensity:.2f}")
    print(f"Standard Deviation of Intensity: {std_intensity:.2f}")

    plt.show()
