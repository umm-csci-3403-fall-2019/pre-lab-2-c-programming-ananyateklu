# Leak report

The memory leak was from the function strip. The leak was created when strip allocated memory for returning result. But, we cannot free the memory from strip since it returns result. however, the function is_clean calls strip and assigns it to the variable cleaned and passes it to strcmp so we can clean it by adding free(cleaned) after strcmp gets called. That doesn't cause any error since strip doesn't get called anywhere else.    

