# Working in Public: The Making and Maintenance of Open Source Software
by Nadia Eghbal

- Most open source projects have only a few dedicated contributors and a lot of low-value interactions
  - Curation, not collaboration occurs
  - Solo maintainers tend to abandon projects due to overwhelming workload
  - Package managers reduce barrier of entry and project commitment
  - GitHub is the dominant platform which functions somewhat like a social media site with an emphasis on creators
  - Open source has evolved just like the rest of the Internet, with tight-knit communities being replaced with large platforms

- Free software evolved into open source software
  - Originally code was published as a tarball (tar bundles files together but without compression) on standalone sites, with mailing lists used for communication
  - Centralized version control (Subversion) was replaced with distributed (Git)
  - Free software hackers - Richard Stallman, Eric Raymond, and Linus Torvalds
    - Linus created Git with no intention of GitHub ever existing
    - Do not want code tied to a platform like GitHub
    - Do not want any proprietary control over code
    - Believe code should not be associated with certain developers
    - Hacker culture = counterculture = extreme
  - Open source advocates are unlike free software advocates since they just want code to be freely used by all, including commercial entities who make their code private
    - Copyleft license (GPL) - preferred by free software, since it forces any code that uses GPL code to also use it
    - Copyright license (MIT) - preferred by open source software, and is the dominant license

- GitHub is the dominant platform today
  - Original platform was SourceForge
  - Current competitor is GitLab, which is open source itself but no one really cares
  - Incorporates some extra features to help with workflow (issue tracking, profiles. pull requests)
  - Helps developers with distribution
  - Even true open source advocates are now rare, people just post code and slap an MIT license on it since GitHub is basically a social media site for code content

- JavaScript is a great representation of modern open source
  - Uses a package manager which results in small, modular code blocks
  - Easy to pick up since you can use a web browser
  - Node.js added JS to the backend
  - The most popular language in the world
  - JS developers act like the opposite of free software hackers
    - Take on too much work from newbies
    - Get overwhelmed with low value interactions

- Project evolution
  1. Starts off private with only a few developers
  2. Gets marketed and gains some users that don&#39;t interact
  3. Starts to see interactions and contributions

- Contribution factors
  - Technical scope - size and complexity of the codebase (amount of work to be done)
  - Support required - amount of work other than commits that need to be done
  - Ease of participation - barrier to entry

- Project types
  - Federations (many contributors, many users)
    - Often broken up into many sub-projects
  - Stadiums (few contributors, many users)
    - Often has a high barrier to entry
    - Relies heavily on curation tools like automation
  - Clubs (many contributors, few users)
  - Toys (few contributors, few users)
  - Federations and clubs are decentralized, while stadiums and toys are centralized
    - Centralized projects are more closely tied to the platform they live on

- Open source is a viable model
  - Firms, at a glance, seem like the only way to manage the resources needed to produce software (effective coordination)
  - Open source is explained as possible using the idea of a commons
    - Self-governed and isolated from other commons
    - Enforces rules and regulations to establish order (sanctions)
      - Members take these seriously because they want to avoid embarrassment and don&#39;t feel like they can simply abandon the community
    - Members are personally motivated to contribute, which reduces coordination costs and results in self-organization, unlike at companies where employees are not volunteers and must be forced to do things
    - Members feel personally attached to the product and their peers
    - Requires intrinsic motivation, modular organization, and small tasks to be successful
      - Money cannot be involved since its an extrinsic motivator and will break the commons model
    - Stadiums do not follow the commons model

- Platforms broke the commons
  - Less sense of shared ownership and dedication
    - Sanctions aren&#39;t effective and have difficult controlling trolls
  - No self-governing rules, since platform standardizes a lot of things
  - GitHub replaced the collective identity of communities with personal identities of each developer
    - Little investment in any project that isn&#39;t their own stadium
  - Unclear membership requirements and community boundaries make it difficult to determine consensus

- Project roles
  - Maintainer - responsible for the project&#39;s overall success and whose decisions are powerful
  - Author - a developer responsible for the projects original release
  - Contributor - contributes to the repo but no responsible for overall success
    - Active contributors have long term interest in the project and community (often higher quality contributions)
    - Casual contributors are self-interested
    - Active and casual contributors may contribute the same amount of code, but each with a different mindset
  - User - uses the project to write code (not an application end-user)
    - May be active externally (creating tutorials, reporting bugs, etc.)
  - A maintainer doesn&#39;t necessarily need to be a author and vice versa
  - Maintainers must weight the value of a contribution long term and consider maintenance costs
  - Maintainers often abandon projects due to a lack of interest and rewards
  - Most developers don&#39;t like maintenance work

- Project health (look at bus factor and other metrics)
  - Bus factor - number of contributors that would need to be hit by a bus before the project dies
  - Number of contributors isn&#39;t a strong metric for project health since casual contributors are often meaningless
  - Also consider these metrics:
    - Number of open issues and pull requests (more is bad)
    - Response time
    - Overall activity (commits, issues, pull requests)
  - Need to consider that some projects do not require much work, so as long as they are stable, they are healthy

- Software has high maintenance costs (which no one wants to deal with)
  - Old technologies never completely die, although maintenance may cease
  - Static code - not used in production (code samples)
  - Active code - used in production and requires maintenance
  - Marginal costs are a function of the number of users
    - Software is incorrectly believed to have zero marginal cost, meaning additional copies are cheap to produce, because it&#39;s non-rivalrous (unlimited resources after initial creation) and non-excludable (naturally distributed to all)
    - Physical infrastructure, user support, and community moderation costs prove that software actually does have marginal costs
      - Physical infrastructure is often handled by external providers but still exists
      - More on this later, but note that these are a part of open source software _production_, not the software product itself
  - Temporal costs are a function of time (decay)
    - Technical debt
      - Scope creep - features keep getting added without considering limited scope of a project, which causes problems in the long run
    - Dependency management, which includes security
    - Changing user needs
      - It&#39;s important to move on from successful and active projects simply to stay competitive

- Software is difficult to monetize, yet is often heavily depended upon
  - Cheap and widespread distribution
  - Absence of scarcity
  - Many viable substitutes
  - Producers find ways to introduce artificial scarcity in software products limited access keys) or introduce hardware dependencies (game consoles)

- The value of code depends on:
  - Number of dependencies
  - Substitutability - ability to substitute with something else that results in no negative consequence
  - Reputation of creators
    - Reputation needs to be maintained by continued content creation

- The government always has their best interest in mind, so they aren&#39;t a strong candidate for managing open source software

- Open source software should actually be thought of as two goods
  - Code - **non-excludable** and **non-rivalrous** as mentioned before
  - Attention - creation participation is **non-excludable** and **rivalrous** , since people are all sharing the limited attention of a few maintainers and the ability to participate is open to everyone
  - The problem doesn&#39;t lie in the code itself, which is a product (positive externality) of participation attention and has zero marginal cost
  - Limiting access to participation, but still making the production process transparent (read-only) is one solution
    - At a minimum, prevent extractive contributions, which are those that aren&#39;t worth the attention that they require

- Managing attention
  - Reducing up-front costs
    - Automated CI, testing, and linting
    - Screening by making high barrier to entry
    - Style guides
    - Issue and PR templates
    - Bots
  - Limiting available attention
    - Giving more attention to contributors based on their number of contributions (more contributions = more attention)
    - One option is to completely block pull requests and only use contributor feedback as inspiration
  - Distributing costs to users
    - Having community members take care of moderation and support
  - Increasing available attention
    - Having a few dedicated co-contributors to take some burden off
    - Isolating large features from the main project and merging them in their entirety only once complete
    - Monetization or employer-provided resources

- Monetization of open source
  - No universal answer
  - In open source, producers can charge for their attention, not the product itself
  - Funders include companies and individuals
    - Companies are more interested in project code over their developers, while individual funders are the opposite
      - Individual funders look for strong individual developer reputations and will give them money directly, enabling them to work on whatever projects they want
    - Companies like to fund products that they use to ensure they are secure and reliable
      - May receive special support services (attention) and be able to influence the project roadmap
      - May end up hiring open source developers full time
    - Companies also may pay for sponsorships
    - Funding from individuals is significantly weaker than from companies since companies will give large amounts
  - Funding should go to maintainers and not contributors, since contributors usually are going to contribute anyway
    - Money is a good motivator for projects in the maintenance stage
  - There are a lot of laws for projects to qualify for funding, so it&#39;s often easier to receive funding as an individual developer directly
    - The project also needs to figure out how to distribute income amongst its members
    - Companies don&#39;t like to fund individual developers, so company funding typically goes to large projects who are willing to set up a funding system that qualifies them

- Platforms need to adapt to the changing world of content creation, where is focus on heavily on individual creators these days
  - Creators are limited by the platforms they live on
  - People would rather lose all past content that a creator has made rather than the creator themselves