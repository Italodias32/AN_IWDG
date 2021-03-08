################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include Drivers/STM32F1xx_HAL_Driver/Src/subdir.mk
-include Core/Startup/subdir.mk
-include Core/Src/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
EXECUTABLES += \
AN_IWDG.elf \

SIZE_OUTPUT += \
default.size.stdout \

OBJDUMP_LIST += \
AN_IWDG.list \

OBJCOPY_BIN += \
AN_IWDG.bin \


# All Target
all: AN_IWDG.elf secondary-outputs

# Tool invocations
AN_IWDG.elf: $(OBJS) $(USER_OBJS) C:\Users\Italo\STM32CubeIDE\workspace_1.3.0\AN_IWDG\STM32F103RBTX_FLASH.ld
	arm-none-eabi-gcc -o "AN_IWDG.elf" @"objects.list" $(USER_OBJS) $(LIBS) -mcpu=cortex-m3 -T"C:\Users\Italo\STM32CubeIDE\workspace_1.3.0\AN_IWDG\STM32F103RBTX_FLASH.ld" --specs=nosys.specs -Wl,-Map="AN_IWDG.map" -Wl,--gc-sections -static --specs=nano.specs -mfloat-abi=soft -mthumb -Wl,--start-group -lc -lm -Wl,--end-group
	@echo 'Finished building target: $@'
	@echo ' '

default.size.stdout: $(EXECUTABLES)
	arm-none-eabi-size  $(EXECUTABLES)
	@echo 'Finished building: $@'
	@echo ' '

AN_IWDG.list: $(EXECUTABLES)
	arm-none-eabi-objdump -h -S $(EXECUTABLES) > "AN_IWDG.list"
	@echo 'Finished building: $@'
	@echo ' '

AN_IWDG.bin: $(EXECUTABLES)
	arm-none-eabi-objcopy  -O binary $(EXECUTABLES) "AN_IWDG.bin"
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) *
	-@echo ' '

secondary-outputs: $(SIZE_OUTPUT) $(OBJDUMP_LIST) $(OBJCOPY_BIN)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
