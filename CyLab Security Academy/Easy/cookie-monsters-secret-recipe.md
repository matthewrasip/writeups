# Cookie Monster's Secret Recipe
#### debug info: [u:953389 e: p: c:469 i:296794]

## Description
Cookie Monster has hidden his top-secret cookie recipe somewhere on his website. As an aspiring cookie detective, your mission is to uncover this delectable secret. Can you outsmart Cookie Monster and find the hidden recipe?

# Approach
Opening the page greets us with a basic login page. Given the name of the challenge, first instinct suggests that checking our cookies might be the next step to solve this question. Upon inspecting our cookies, we see a cookie named `secret_recipe`, with the value `cGljb0NURntjMDBrMWVfbTBuc3Rlcl9sMHZlc19jMDBraWVzXzczMTEwRUQxfQ%3D%3D`. Trying to use a base64 decoder with the encoded value, we receive the flag:
```
picoCTF{c00k1e_m0nster_l0ves_c00kies_73110ED1}
```