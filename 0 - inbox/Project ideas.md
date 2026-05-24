---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2026-05-24T10:37
---
---


let me be more straight about it. i know next to nothing about mcp servers. What I already know is that MCP servers somehow lead to agents and that now llms were able to access different tools to do more things. what I dont know is how to use them as I have never used them before. 

so first tell me some methods which I can try to understand them better. 

second my understanding of the current idea is that it should be something like an npm library for mcps ? am I right? if yes that I dont want to directly jump into best tech stack to build this but hold on to learn more about anything you can give me. It doessnt have to be in a single prompt answer you can first give me a curriculumn and then we can further move as we go. 

also what I do understand about current available marketplaces is that while they are avaiable I am assuming that they are themselves updating the verion or repo? Idk how do you make your library go into npm. I think you upload register and give an endpoint to download the latest one? idk 

and how will we replicate this for MCP servers?

while I hardly understand the points you are making especially the first 4 ones. 

I want to know how will it be related to npx because we are going to build our own thing ig? I amt sure?

I want to know when you say while the official one is not released then is there any official org that if introduces a marketplace then will be consdered the official one?

also idk how does these existing marketplaces include mcp servers in them? ig developers of these mcp servers register themselves? also how will I make mine the official registy? how will I set the authority?

is this mcp-hub name registered somewhere or you are suggesting this name for the project?

who is the official registry and when is it coming? and what do you mean by mindshare(is it like developers mind term for marketshare?)

tbh I think this project is bigger than me. Idk if I have the technical expertise to build it but I want to go on anyways. I need your help. I want this to be THE npm of mcp and one thing I dont understand is why would we have to have npx to download it? like npx is from npm and if we are building something equivalent then does that mean we havt to get something of similar level like npx in future if not now?

yes I want readme and architecture but first I want you to help with all above

correct me anywhere needed and add any possible tips, suggestions or advices you can

---

yeah npx is just download and run but not install but npx must be downloading from npm registry right? 

so the current marketplaces dont even have some way to register and the marketplace owner have to do it manually? 

how is linux foundation buildng the official registry? like have they started or mentioned anywhere that they are eventually going to come up with it? 

are you seriously saying me ( just a junior developer ) can build something on par with linux foundation and that too alone? 

i have another upgrade idea. the current setup where you might have to install that ai(like claude)'s desktop version to have it manage the mcp servers if it does and have them connect we can do an mcp hub desktop app which website like claude can connect to with some way (possibly api key or ssh key ) and then you can directly send request to mcp hub in desktop to do these with these mcp and it will do it? 

also instead of having anthropic mcp config and different one for each tool we can standardize it with mcpconfig.py or something?

the first thing I want to say is that create a .md doc which includes everything about the project mcp marketplace we have discussed up until now. it should be well documented. Sequence wise like a proper project document. The reason being I want a centralised document for my project to know all the things realated which I can in future give you also as a context for further discussion.

dont say how does mcp install actually work like there is already a tool making it work. Write how it will soon work or how it will work. Yes as much as I love to host the code I amnt sure if I can handle the cloud cost. How does other marketplaces do that? Yes I dont want to end up being just a fancier directory so yes I want to host it but idk how. The problem apart from being a fancier directory is that if in future for a particular version some changes or bugs occur which causes mcp install to fail then it will be bad. 

this also makes me arrive at the question like do I want to make all these three things which is site and registry and cli together or slowly develop each. And a lot of questions.


---


one thing I am very concerned about is the desktop version being able to manage the permissions. Is this even possible and what is the engienering difficulty of this ? 

so for mcp install to work I would need to do some software to be installed just like we install node for using npm. And is this deamon idea even good or we should implement a different model? I dont know? If we were just doing npm thing then ig deamon wouldnt have been needed but for desktop ig it's normal that we have a way to either for desktop to use cli in backgroup or deamon?


---

if I upload 50 famous servers then I contact them saying I have added your server and you want to add a mcp.json? then if they say that from now on I want to be the only one to publish/unpublish this mcp on it then how can I have them an account created and attach that server to that account an then hand it to them. during phrase 1 how do I implement sha256 hash verifying thing on download as the download will be coming direcctly from github and I wouldnt have a tarball and it's hashcode saved to verify it from? 

In phrase 1 you have witten for week 1 and 2 that I setup the project repo and write docs. Which type of docs? 

an idea as I am bulding a lot of commands for my cli, we can implement rag in our website backend and have it being able to answer more about the project and it will have reference to the doc that we have for plugd and if some developer wants to do something like plug rollback --list but he doesnt know this command then it can come to chatbot and ask how do I get back to the version before changes and chatbot will give a short answer with reference to the original doc line where this info was mentioned.

one major upgrade I think we can have is track of each calls for mcp by each ai agent when, how long, etc which tells things.

maybe we can create a swtich for permissions. Like if an mcp server requires 3 permission but user only agree with two then user can have third blocked with deamon.

so in current market scenairo for gap 7. Everyone is storing token in config right? if yes then option A is the obvous choice as we are offering something better while not restricting the user. Also in phrase 1 we cant have warning because if user does try to install plugd deamon then we have nothing to ship. Also I really need you to make me understand this secrets things better. Like secrets thing is us storing the secrets in keychain if bool value is true and storing it ig in config only if it's false? clear that up. so Ig I do need to register my name in bun and in pnpm too.

and yes your suggestion for monorepo setup with pnpm and build cli tool with bun is corrent and I love to lock it.

you said check before every pr. but arent I the owner of repo so would I just do push instead of pr?

---

so when exactly is time for tarballs? it looks like a very imp feature to me now and we should do it in phrase 1 ig?

wdym one owner and other collaborators. Like collaborators can also publish..? or what?

for the chatbot claude answers with reference. It will cost claude api ig? but if we are to phrase 3 then ig it's okay. We can see some less expensive more able to handle crowd api. Also we have to apply rate limit and all. Are you sure claude API for the answers is cheap?

yes we can have chatbot in phrase 2 end with low priority or phrase 3

i like the new phrasing for os keychain in phrase 1.

what I need you to do is make another file of all the decisions we have discussed and taken until now. So I can give it as context to other ai.


