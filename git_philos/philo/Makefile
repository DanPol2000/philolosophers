# **************************************************************************** #
#                                                                              #
#                                                         :::      ::::::::    #
#    Makefile                                           :+:      :+:    :+:    #
#                                                     +:+ +:+         +:+      #
#    By: chorse <chorse@student.42.fr>              +#+  +:+       +#+         #
#                                                 +#+#+#+#+#+   +#+            #
#    Created: 2022/04/16 14:31:42 by chorse            #+#    #+#              #
#    Updated: 2022/05/26 14:24:17 by chorse           ###   ########.fr        #
#                                                                              #
# **************************************************************************** #

NAME = philo

CC = gcc

CFLAGS = -Wall -Werror -Wextra -MMD -fsanitize=address -g

INC = philo.h

SRC	   = main.c usage.c init.c monitoring.c live.c\

OBJ = $(patsubst %.c,%.o,$(SRC))

D_OBJ = $(patsubst %.c,%.d,$(SRC))

all : $(NAME)

$(NAME) : $(OBJ)
	@echo "\033[0;33m\n\nCompiling philosophers..."
	@$(CC) $(CFLAGS) $(OBJ) -o $(NAME)
	@echo "\n\033[0;36mDone."

%.o : %.c $(INC)
	@printf "\033[0;34mGenerating philosophers objects... %-10.10s\r" $@
	gcc $(CFLAGS) -c $< -o $@

clean :
	@echo "\033[0;31m\nDeleting objects..."
	rm -f $(OBJ) $(D_OBJ)
	@echo "\n\033[0;31mDeleted.\n"

fclean : clean
	rm -f $(NAME)

re : fclean all

.PHONY : all clean fclean re
