# STM32 GPIO LED Blink (STM32F446RE)

This project is a basic example of toggling GPIO pins on the STM32F446RE Nucleo board using STM32CubeIDE and the STM32 HAL (Hardware Abstraction Layer) library.

## 🔧 Project Overview

- **Board**: STM32F446RE Nucleo
- **IDE**: STM32CubeIDE
- **Language**: C (HAL-based)
- **Functionality**:
  - Toggles two GPIO output pins (PC5 and PA5) with a 1-second delay.
  - Useful for testing basic GPIO configuration and understanding HAL functions.
 
    ## 🚦 GPIO Configuration

| Pin   | Port | Mode         | State      |
|-------|------|--------------|------------|
| PA5   | A    | Output Push-Pull | Blinks after PC5 |
| PC5   | C    | Output Push-Pull | Blinks first     |

## 🕒 Delay Details

- Each pin remains ON for 1 second, then turns OFF.
- The next pin turns ON, and the pattern repeats.

## 💡 How It Works

```c
while (1)
{
    HAL_GPIO_WritePin(GPIOC, GPIO_PIN_5, GPIO_PIN_SET);
    HAL_Delay(1000);
    HAL_GPIO_WritePin(GPIOC, GPIO_PIN_5, GPIO_PIN_RESET);

    HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
    HAL_Delay(1000);
    HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
}



