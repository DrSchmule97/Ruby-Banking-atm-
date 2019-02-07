# Ruby-Banking-ATM
require_relative "rubyatm"
@users = []
@current_user ="" 
def welcome_screen
p "Welcome to TTS Bank"
p "Please select a number from the following"
p "---------------------------"
p "1:Login"
p "2:Register"
p "---------------------------"
response = gets.chomp.to_i  
	if response == 1
		login_customer 
		#login cutsomer 
		p "response1"
	elsif response == 2 
		p "response2"
		#register customer
	else 
		p "Unrecognized response. Try again."
		welcome_screen
	end 

		def register_customer
				p "Please enter your name"
				customer_name = gets.chomp
				p "Please enter your email"
				email = gets.chomp
				p "Please create a password"
				password = gets.chomp
				new_user = Customer.new(name, password, email)
				@users.push(new_user)
				@current_user = new_user
				login_customer
		end 

	def login_customer 
				p "What is your email?"
			email = gets.chomp
				p "What is your password?"
			password = gets.chomp
		
		if @users.empty?
		 		p "User does not exist"
				@users.each do |user| if email == @users.email && password == user.password
				p " Welcome#{user.name}"
			   	@current_user = user 
			 else 
			 	p "Please try again"
			 	p "If you are a new customer, use the register option"
			 	welcome_screen 
			 end 
			end
		end
	end
end

def account_screen 
	p "Welcome to your account #{@current_user.name}"
	p "Please select from the following options"
	p "----------------------------------------"
    p "1: Create Account"
    p "2: View Accounts"
    p "3: logout"
    response = gets.chomp.to_i 
    case response
    when 1
    	create_account
    when 2
    when 3 
    else 
    	p "Unrecognized response. Try Again"
    	account_screen
    end 
end 

def create_account 
	#(account_num, balance, type, customer)
 p "what kind of account?"
 type = gets.chomp 
 p "What is your starting balance"
 bal = gets.chomp 
 account_num = @users.size += 1 
 new_account = Account.new 
 @current_user.accounts.push(new_accounts)
welcome_screen
