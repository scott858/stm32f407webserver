################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include src/syscalls/subdir.mk
-include src/stdio/subdir.mk
-include src/cmsis_lib/source/subdir.mk
-include src/cmsis_boot/startup/subdir.mk
-include src/cmsis_boot/subdir.mk
-include src/STM32F4x7_ETH_Driver/src/netif/ppp/subdir.mk
-include src/STM32F4x7_ETH_Driver/src/netif/subdir.mk
-include src/STM32F4x7_ETH_Driver/src/core/snmp/subdir.mk
-include src/STM32F4x7_ETH_Driver/src/core/ipv4/subdir.mk
-include src/STM32F4x7_ETH_Driver/src/core/subdir.mk
-include src/STM32F4x7_ETH_Driver/src/api/subdir.mk
-include src/STM32F4x7_ETH_Driver/src/subdir.mk
-include src/Ethernet/source/subdir.mk
-include src/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(CC_DEPS)),)
-include $(CC_DEPS)
endif
ifneq ($(strip $(C++_DEPS)),)
-include $(C++_DEPS)
endif
ifneq ($(strip $(C_UPPER_DEPS)),)
-include $(C_UPPER_DEPS)
endif
ifneq ($(strip $(CXX_DEPS)),)
-include $(CXX_DEPS)
endif
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
ifneq ($(strip $(CPP_DEPS)),)
-include $(CPP_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
SECONDARY_FLASH += \
stm32f407webserver.hex \

SECONDARY_SIZE += \
stm32f407webserver.siz \


# All Target
all: stm32f407webserver.elf secondary-outputs

# Tool invocations
stm32f407webserver.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: Cross ARM C++ Linker'
	arm-none-eabi-g++ -mcpu=cortex-m4 -mthumb -mfloat-abi=soft -Og -fmessage-length=0 -fsigned-char -ffunction-sections -fdata-sections -fno-move-loop-invariants -Wall -Wextra  -g3 -T mem.ld -T libs.ld -T sections.ld -nostartfiles -Xlinker --gc-sections -L"../ldscripts" -Wl,-Map,"stm32f407webserver.map" --specs=nano.specs -o "stm32f407webserver.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

stm32f407webserver.hex: stm32f407webserver.elf
	@echo 'Invoking: Cross ARM GNU Create Flash Image'
	arm-none-eabi-objcopy -O ihex "stm32f407webserver.elf"  "stm32f407webserver.hex"
	@echo 'Finished building: $@'
	@echo ' '

stm32f407webserver.siz: stm32f407webserver.elf
	@echo 'Invoking: Cross ARM GNU Print Size'
	arm-none-eabi-size --format=berkeley "stm32f407webserver.elf"
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(CC_DEPS)$(C++_DEPS)$(OBJS)$(C_UPPER_DEPS)$(CXX_DEPS)$(SECONDARY_FLASH)$(SECONDARY_SIZE)$(ASM_DEPS)$(S_UPPER_DEPS)$(C_DEPS)$(CPP_DEPS) stm32f407webserver.elf
	-@echo ' '

secondary-outputs: $(SECONDARY_FLASH) $(SECONDARY_SIZE)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
