```typescript
interface Hacker {
  break(target: Scope): Report // only with written permission
}

interface Developer {
  build(idea: Idea): Production // end to end, front to back
}

class Muhammed implements Hacker, Developer {
  readonly speaks = ["Arabic", "English"]

  get whoami(): { now: string[]; past: string[] } {
    return {
      now: ["full-stack developer", "security researcher", "building Flint (flint.ps)"],
      past: ["Trusted Security Researcher @ Meta — web, Android & iOS"],
    }
  }

  get coding(): Record<"expert" | "advanced" | "focus" | "offense", string[]> {
    return {
      expert: ["Laravel", "Vue"],
      advanced: ["Go", "Rust", "TypeScript", "JavaScript", "React", "Node", "PHP", "Python", "Tailwind"],
      focus: ["application security", "reverse engineering", "full-stack web"],
      offense: ["Burp Suite", "Frida", "jadx", "mitmproxy"],
    }
  }

  // find the bug before someone else does.
  break(target: Scope): Report {
    if (!target.authorized) throw new Error("consent first, always")
    return this.recon(target).exploit().writeup({ repro: true })
  }

  // then build the thing that doesn't have it.
  build(idea: Idea): Production {
    return this.design(idea).ship() // small, often, in production
  }

  get contact(): Record<string, string> {
    return {
      email: "hi@mumd.dev",
      github: "iMumd",
    }
  }
}

export default new Muhammed()
```
