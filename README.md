# hondacircuit
An archive/playable offline version of the 2019 Honda promotional game

To run the game, you need to have Node.JS installed.
Simply run the .bat file to run the server.

To unlock all of the levels, you need to go into the developer console (ctrl + shift + i) and run this command.

   const _fetch = window.fetch;
   window.fetch = (url, opts) =>
     String(url).endsWith('/ts')
       ? Promise.resolve(new Response(
           JSON.stringify({ payload: { actual_date: '2020-01-01 12:00:00' } }),
           { status: 200, headers: { 'Content-Type': 'application/json' } }))
       : _fetch(url, opts);
