# Name of the project
PROJECT_NAME = vaccine

# Output directory
BUILD = build

# All source code files
SRC = main.c\
src/create_ll.c \
src/display_ll.c \
src/insert_end.c \
src/find_by_id.c \
src/update_record.c \
src/indexFile.c \
src/validate_id.c \
src/openFile.c \
src/saveFile.c \
src/readFile.c \
src/loadData.c \
src/update_data_file.c \
src/delete_patient.c \
src/delete_rec_file.c \
src/delete_all.c



# All test source files
TEST_SRC =  test/test.c \
unit/unity.c \

TEST_OUTPUT = $(BUILD)/Test_$(PROJECT_NAME).exe

# All include folders with header files
INC	= -Iinc\
-Iunit

#Library Inlcudes
#if working with CUnit 
#INCLUDE_LIBS = -lcunit
INCLUDE_LIBS =

# Project Output name
PROJECT_OUTPUT = $(BUILD)/$(PROJECT_NAME)

# Document files
DOCUMENTATION_OUTPUT = documentation/html

# Default target built
$(PROJECT_NAME):all

# Run the target even if the matching name exists
.PHONY: run clean test doc all

all: $(SRC) $(BUILD)
	gcc $(INC) $(SRC) -o $(PROJECT_OUTPUT).exe

# Call `make run` to run the application
run:$(PROJECT_NAME)
	./$(PROJECT_OUTPUT).exe

# Document the code using Doxygen
#doc:
#	make -C ./documentation

# Build and run the unit tests
test:$(BUILD)
	 gcc -I $(TEST_SRC) $(INC) -o $(TEST_OUTPUT)
	 ./$(TEST_OUTPUT).exe
#Coverage
coverageCheck:$(BUILD)
	g++ -fprofile-arcs -ftest-coverage -fPIC -O0 $(TEST_SRC) $(INC) -o $(TEST_OUTPUT)
	./$(TEST_OUTPUT)

# Remove all the built files, invoke by `make clean`
clean:
	rm -rf $(BUILD) $(DOCUMENTATION_OUTPUT)

# Create new build folder if not present
$(BUILD):
	mkdir build
