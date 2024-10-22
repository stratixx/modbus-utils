cmake_minimum_required(VERSION 3.18)
project(modbusUtils)

add_executable(modbus-dump src/modbus-dump.c src/common.c)
add_executable(modbus-set src/modbus-set.c src/common.c)
add_executable(modbus-test src/modbus-test.c src/common.c)

target_compile_definitions(modbus-dump PRIVATE program_invocation_short_name="modbus-dump")
target_compile_definitions(modbus-set PRIVATE program_invocation_short_name="modbus-set")
target_compile_definitions(modbus-test PRIVATE program_invocation_short_name="modbus-test")

target_link_libraries(modbus-dump modbus)
target_link_libraries(modbus-set modbus)
target_link_libraries(modbus-test modbus)

install(TARGETS modbus-dump DESTINATION /usr/bin)
install(TARGETS modbus-set DESTINATION /usr/bin)
install(TARGETS modbus-test DESTINATION /usr/bin)
