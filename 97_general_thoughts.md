# General Thoughts

Remember there's no perfect solution out there. Everything has some pros/cons and it always `depends on:`

- use case
- skillsets of your teammates
- how much effort do you want to spend on developing "a tight-fit, top-notch" solution
- personal preferences

At the end what really matters is the final value which your code brings to the team/project.

## DevOps

- make your code as generic as possible
- reuse your code whenever it suits
- avoid duplication of code
- don't forget about idempotency
  - if your automation tool/framework etc. doesn't support it, you will need to handle it by yourself
    - i.e.: using `changed_when:` and `failed_when:` parameters when using `shell:` Ansible module

- test your stuff (not only in CI but locally too)
  - give people an option to test things locally the same way as it's done in your CI pipeline

- and hey trust people, give them an option to make mistakes
  - we learn the most from them ;)
- and don't forget: if you break something, you fix it x)

## Some useful links and tools

- awesome-sites
  - k8s - <https://github.com/ramitsurana/awesome-kubernetes>
  - docker - <https://github.com/veggiemonk/awesome-docker>
  - ...
- readme.md template: <https://github.com/othneildrew/Best-README-Template>

- game of pods
  - <https://kodekloud.com/p/game-of-pods>
