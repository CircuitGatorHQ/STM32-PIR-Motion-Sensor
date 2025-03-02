# STM32-PIR-Motion-Sensor
This is a very simple code you can run on your STM32 microcontroller to detect motion using the HC-SR501 PIR sensor. The full video tutorial is available on YouTube: 

    /* Private includes ----------------------------------------------------------*/
    /* USER CODE BEGIN Includes */
    #include <string.h>
    /* USER CODE END Includes */
    
    /* USER CODE BEGIN PV */
    int motion;
    char msg1[] = "Motion Detected!\r\n";
    char msg2[] = "         \r\n";
    /* USER CODE END PV */
    
    
      /* USER CODE BEGIN WHILE */
      while (1)
      {
        /* USER CODE END WHILE */
    
        /* USER CODE BEGIN 3 */
    	  motion = HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_8); // Read PIR state
    	  if (motion == 1){
    	  HAL_UART_Transmit(&huart2, (uint8_t*)msg1, strlen(msg1), HAL_MAX_DELAY);
    	  }
    	  else if (motion == 0 ){
    	  HAL_UART_Transmit(&huart2, (uint8_t*)msg2, strlen(msg2), HAL_MAX_DELAY);
    	  }
      }
      /* USER CODE END 3 */
    }
