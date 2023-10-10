NAME=s21_cat
CC=gcc
CFLAGS=-Wall -Werror -Wextra -std=c11 -g 

all: $(NAME)

$(NAME): $(NAME).c
	$(CC) $(CFLAGS) $(NAME).c -o $(NAME)

clean:
	rm -rf $(NAME) *.log *.dSYM
docker_test:
	sh ../../materials/build/run.sh
test:
	sh test_func_cat.sh
clang:
	cp ../../materials/linters/.clang-format ./
	clang-format -n *.c
	rm -rf .clang-format
leak:
	leaks -atExit -- ./$(NAME)
check:
	clang-format -style=Google -n *.c

rebuild:
	$(MAKE) clean
	$(MAKE) all
