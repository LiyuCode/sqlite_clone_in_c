# with comment

No backgroud of Ruby, some comments on understanding the logic of the script.

```rb
# 1.Here I want to test an executable
describe 'database' do
    # 3. How to run the Input/ExpOpt paris?
    def run_script(commands)
        raw_output = nil
        # 4. 1st, run `./db.out`
        IO.popen("./db.out","r+") do |pipe|
            # 5. 2nd, continuously type the inputs in the pairs
            commands.each do |command|
                pipe.puts command
            end

            pipe.close_write

            # 6. 3rd, record all the outputs
            raw_output = pipe.gets(nil)
        end
        raw_output.split("\n")
    end
    # 2. A serial of paired <input, expected output>
    it 'inserts and retrieves a row' do
        result = run_script([
            "insert 1 user1 person1@example.com",
            "select",
            ".exit",
        ])
        expect(result).to match_array([
            "db > Executed.",
            "db > (1, user1, person1@example.com)",
            "Executed.",
            "db > ",
        ])
    end
end

```