# zip-solver

## Zip Puzzle Builder and Solver

As an experiment I built a solver for the fun Zip puzzles on LinkedIn, e.g.:

https://www.linkedin.com/games/zip/

100% with AI.  I did not write a single line of code.

## Rules of Zip

1. You must find a complete path between the nodes on the grid in numerical order
2. You can travel in straight lines and turn.
3. You can only turn 90 degrees in a single cell
4. You must visit every cell in the grid
5. You must not cross your own path
6. There are sometimes walls on the edges of cells and your path can't cross them either.

## How I built the tool

I used `o3` on ChatGPT initially to solve a puzzle from a screenshot from LinkedIn with a short text description of the rules.  It did it in 2 shots after a short clarfication about not being able to cross your own path.

Not content with challenging OpenAI with just solving a day's puzzle, I decided to task it with building a web tool that allowed you to build and solve the puzzles automatically.

I initially started with `o3` on ChatGPT but eventually switched to [Codex](https://github.com/openai/codex) and `o4-mini`

I worked with o3 for about 2 hours, and o4 for about 1 minute (to fix a bug).

What was interesting was transferring from `o3` on ChatGPT to `o4-mini` on the "command line" with Codex did not cause an issue and `o4=mini` was able to pick up where `o3` left off.  I gave o4 an English summary on what the code did, but it did not have the benefit of all the context from ChatGPT conversation.

## Issues I encountered (at time of writing):

* `o3` undoing work that it had already completed successfully
* Really trivial errors like getting comment delimiting wrong when all the really hard stuff had been done perfectly!
* `o3` started to stop finishing its work and Canvas was showing only 2/3rds of the code it had already written (hence ultimate transfer to Codex)

Definitely an interesting experience.  I know these tools can struggle with bigger codebases but single page javascript widgets like this appear conquered.
