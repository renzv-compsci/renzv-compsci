
local function deep_freeze(t)
  -- Recursively freeze a table by setting a metatable that prevents write operations.
  for k, v in pairs(t) do
    if type(v) == "table" then
      deep_freeze(v)
    end
  end
  return setmetatable(t, {
    __newindex = function()
      error("attempt to modify read-only table", 2)
    end,
    __metatable = false
  })
end

local PROFILE = {
  name = "Renz",
  full_name = "Renz Viloria",
  github = "renzv-compsci",
  bio = "CS Student @ National University — passionate about AI, Game Dev & Automation",
  interests = {
    "AI & Automation",
    "Data Science",
    "Game Development",
    "Web & App Development",
    "Computer Vision",
    "Esports",
    "Urban Sketching"
  },
  learning = {
    "Python & Machine Learning",
    "Java (GUI & Games)",
    "Operating Systems",
    "App / Web Development"
  },
  tech = {
    frontend = {
      { name = "React",    icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" },
      { name = "HTML5",    icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" },
      { name = "CSS3",     icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" },
      { name = "JavaScript",icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" }
    },
    backend = {
      { name = "Java",        icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" },
      { name = "Spring Boot", icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spring/spring-original.svg" },
      { name = "Python",      icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" },
      { name = "Firebase",    icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/firebase/firebase-plain.svg" }
    },
    ml_ds = {
      { name = "Python",     icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" },
      { name = "Pandas",     icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pandas/pandas-original.svg" },
      { name = "Scikit-learn", icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/scikitlearn/scikitlearn-original.svg" }
    },
    game_dev = {
      { name = "Godot", icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/godot/godot-original-wordmark.svg" },
      { name = "SDL",   icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sdl/sdl-original.svg" },
      { name = "Lua",   icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/lua/lua-original.svg" }
    },
    databases = {
      { name = "SQLite",    icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sqlite/sqlite-original.svg" },
      { name = "PostgreSQL",icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" },
      { name = "Firebase",  icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/firebase/firebase-plain.svg" }
    },
    systems = {
      { name = "C", icon = "https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" }
    }
  },
  contact = {
    email = "viloriarenz917@gmail.com",
    linkedin = "https://www.linkedin.com/in/renz-viloria-b8035634b/"
  },
  github_stats_images = {
    commits = "https://github-readme-stats.vercel.app/api?username=renzv-compsci&theme=one_dark_pro&hide_border=false&include_all_commits=false&count_private=true",
    streak  = "https://nirzak-streak-stats.vercel.app/?user=renzv-compsci&theme=one_dark_pro&hide_border=false",
    top_langs = "https://github-readme-stats.vercel.app/api/top-langs/?username=renzv-compsci&theme=one_dark_pro&hide_border=false&include_all_commits=false&count_private=true&layout=compact"
  }
}

-- Freeze the table to emulate a const (read-only) table
deep_freeze(PROFILE)

-- Return the constant-like profile for use as a module
return PROFILE
