################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include MCAL/DIO/subdir.mk
-include MCAL/ADC/subdir.mk
-include HAL/LCD/subdir.mk
-include HAL/FLEX_SENSOR/subdir.mk
-include APP/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
GLOVE_FOR_DEAF.lss \

FLASH_IMAGE += \
GLOVE_FOR_DEAF.hex \

SIZEDUMMY += \
sizedummy \


# All Target
all: GLOVE_FOR_DEAF.elf secondary-outputs

# Tool invocations
GLOVE_FOR_DEAF.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,GLOVE_FOR_DEAF.map -mmcu=atmega32 -o "GLOVE_FOR_DEAF.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

GLOVE_FOR_DEAF.lss: GLOVE_FOR_DEAF.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S GLOVE_FOR_DEAF.elf  >"GLOVE_FOR_DEAF.lss"
	@echo 'Finished building: $@'
	@echo ' '

GLOVE_FOR_DEAF.hex: GLOVE_FOR_DEAF.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex GLOVE_FOR_DEAF.elf  "GLOVE_FOR_DEAF.hex"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: GLOVE_FOR_DEAF.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega32 GLOVE_FOR_DEAF.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) GLOVE_FOR_DEAF.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
